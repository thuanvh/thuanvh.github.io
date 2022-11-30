---
layout: post
title: Optimize SQL query for select top N rows

---
https://www.itprotoday.com/sql-server/optimizing-top-n-group-queries

```
IF OBJECT_ID('dbo.test_GetNums', 'IF') IS NOT NULL DROP FUNCTION dbo.test_GetNums;
GO
CREATE FUNCTION dbo.test_GetNums(@n AS BIGINT) RETURNS TABLE
AS
RETURN
  WITH
  L0   AS(SELECT 1 AS c UNION ALL SELECT 1),
  L1   AS(SELECT 1 AS c FROM L0 AS A CROSS JOIN L0 AS B),
  L2   AS(SELECT 1 AS c FROM L1 AS A CROSS JOIN L1 AS B),
  L3   AS(SELECT 1 AS c FROM L2 AS A CROSS JOIN L2 AS B),
  L4   AS(SELECT 1 AS c FROM L3 AS A CROSS JOIN L3 AS B),
  L5   AS(SELECT 1 AS c FROM L4 AS A CROSS JOIN L4 AS B),
  Nums AS(SELECT ROW_NUMBER() OVER(ORDER BY (SELECT NULL)) AS n FROM L5)
  SELECT TOP(@n) n FROM Nums ORDER BY n;
GO

DECLARE
  @num_orders      AS INT     ,
  @num_customers   AS INT     ,
  @num_employees   AS INT     ,
  @num_shippers    AS INT     ,
  @start_orderdate AS DATETIME,
  @end_orderdate   AS DATETIME;
 
SELECT
  @num_orders      =    1000000,
  @num_customers   =      50000,
  @num_employees   =    400,
  @num_shippers    =     10,
  @start_orderdate = '20060101',
  @end_orderdate   = '20100531';
 
IF OBJECT_ID('dbo.test_Orders'   , 'U') IS NOT NULL DROP TABLE dbo.test_Orders;
IF OBJECT_ID('dbo.test_Customers', 'U') IS NOT NULL DROP TABLE dbo.test_Customers;
IF OBJECT_ID('dbo.test_Employees', 'U') IS NOT NULL DROP TABLE dbo.test_Employees;
IF OBJECT_ID('dbo.test_Shippers' , 'U') IS NOT NULL DROP TABLE dbo.test_Shippers;
 
-- Customers
CREATE TABLE dbo.test_Customers
(
  custid   INT     NOT NULL,
  custname VARCHAR(50) NOT NULL,
  filler   CHAR(200)   NOT NULL DEFAULT('a'),
  CONSTRAINT PK_Customers PRIMARY KEY(custid)
);
 
INSERT INTO dbo.test_Customers WITH (TABLOCK) (custid, custname)
  SELECT n, 'Cust ' + CAST(n AS VARCHAR(10)) FROM dbo.test_GetNums(@num_customers);
 
-- Employees
CREATE TABLE dbo.test_Employees
(
  empid   INT     NOT NULL,
  empname VARCHAR(50) NOT NULL,
  filler  CHAR(200)   NOT NULL DEFAULT('a'),
  CONSTRAINT PK_Employees PRIMARY KEY(empid)
);
 
INSERT INTO dbo.test_Employees WITH (TABLOCK) (empid, empname)
  SELECT n, 'Emp ' + CAST(n AS VARCHAR(10)) FROM dbo.test_GetNums(@num_employees);
 
-- Shippers
CREATE TABLE dbo.test_Shippers
(
  shipperid   INT     NOT NULL,
  shippername VARCHAR(50) NOT NULL,
  filler      CHAR(200)   NOT NULL DEFAULT('a'),
  CONSTRAINT PK_Shippers PRIMARY KEY(shipperid)
);
 
INSERT INTO dbo.test_Shippers WITH (TABLOCK) (shipperid, shippername)
  SELECT n, 'Shipper ' + CAST(n AS VARCHAR(10)) FROM dbo.test_GetNums(@num_shippers);
 
-- Orders
CREATE TABLE dbo.test_Orders
(
  orderid    INT       NOT NULL,
  custid     INT       NOT NULL,
  empid      INT       NOT NULL,
  shipperid      INT       NOT NULL,
  orderdate      DATETIME  NOT NULL,
  shipdate       DATETIME  NULL,
  filler     CHAR(200) NOT NULL DEFAULT('a'),
  CONSTRAINT PK_Orders PRIMARY KEY(orderid),
);
 
WITH C AS
(
  SELECT
    n AS orderid,
    ABS(CHECKSUM(NEWID())) % @num_customers + 1 AS custid,
    ABS(CHECKSUM(NEWID())) % @num_employees + 1 AS empid,
    ABS(CHECKSUM(NEWID())) % @num_shippers  + 1 AS shipperid,
    DATEADD(day,
        ABS(CHECKSUM(NEWID()))
      % (DATEDIFF(day, @start_orderdate, @end_orderdate) + 1),
        @start_orderdate) AS orderdate,
    ABS(CHECKSUM(NEWID())) % 31 AS shipdays
  FROM dbo.test_GetNums(@num_orders)
)
INSERT INTO dbo.test_Orders WITH (TABLOCK) (orderid, custid, empid, shipperid, orderdate, shipdate)
  SELECT orderid, custid, empid, shipperid, orderdate,
    CASE
  WHEN DATEADD(day, shipdays, orderdate) > @end_orderdate THEN NULL
  ELSE DATEADD(day, shipdays, orderdate)
    END AS shipdate
  FROM C;


  CREATE UNIQUE NONCLUSTERED INDEX idx_unc_sid_odD_oidD_Ifiller
  ON dbo.test_Orders(shipperid, orderdate DESC, orderid DESC)
  INCLUDE(filler);

CREATE UNIQUE NONCLUSTERED INDEX idx_unc_cid_odD_oidD_Ifiller
  ON dbo.test_Orders(custid, orderdate DESC, orderid DESC)
  INCLUDE(filler);


WITH C AS
(
  SELECT custid, orderdate, orderid, filler,
    ROW_NUMBER() OVER(PARTITION BY custid
          ORDER BY orderdate DESC, orderid DESC) AS rownum
  FROM dbo.test_Orders
)
SELECT custid, orderdate, orderid, filler
FROM C
WHERE rownum = 1;

SELECT A.*
FROM dbo.test_Customers AS C
  CROSS APPLY (SELECT TOP (1) custid, orderdate, orderid, filler
       FROM dbo.test_Orders AS O
       WHERE O.custid = C.custid
       ORDER BY orderdate DESC, orderid DESC) AS A;

WITH C AS
(
  SELECT
    custid,
    MAX((CONVERT(CHAR(8), orderdate, 112)
     + RIGHT('000000000' + CAST(orderid AS VARCHAR(10)), 10)
     + filler) COLLATE Latin1_General_BIN2) AS string
  FROM dbo.test_Orders
  GROUP BY custid
)
SELECT custid,
  CAST(SUBSTRING(string,  1,   8) AS DATETIME ) AS orderdate,
  CAST(SUBSTRING(string,  9,  10) AS INT      ) AS orderid,
  CAST(SUBSTRING(string, 19, 200) AS CHAR(200)) AS filler
FROM C;


DROP INDEX
  dbo.test_Orders.idx_unc_sid_odD_oidD_Ifiller,
  dbo.test_Orders.idx_unc_cid_odD_oidD_Ifiller;
```

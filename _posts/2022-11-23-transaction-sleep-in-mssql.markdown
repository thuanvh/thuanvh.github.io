---
layout: post
title: Transaction sleep in mssql

---
One of problem in these days that I must face to is leaking transaction.
After a long runtime, one day a DBA person tell me about a sleeping transaction.
The transaction is sleeping for hours that causes a database blocking.

Solution:
Call `If @@TRANCOUNT > 0 ROLLBACK TRAN;` in any exception catch of a transaction process.
```
try{

}catch(Exception ex){
  // Call If @@TRANCOUNT > 0 ROLLBACK TRAN;
}
```

`If @@TRANCOUNT > 0 ROLLBACK TRAN;` is for terminate all opening transaction of current connection.


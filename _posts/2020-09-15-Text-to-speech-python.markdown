---
layout : post
---
There is a simple way to get text to speech from Google.
In python, there is a library gTTS.

```
pip install gTTS
pip install gtts-token
```

Using:
```
from gtts import gTTS
tts = gTTS('Hello', lang='en')
tts.save('hello.mp3')
```

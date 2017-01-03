---
published: true
title: Linux & mac admin tips & tricks
---
## found the pid of a listening process + kill it

I found this [Stackoverflow](http://stackoverflow.com/questions/24387451/how-can-i-kill-whatever-process-is-using-port-8080-so-that-i-can-vagrant-up) question.

On MAC
```
lsof -i tcp:8018
```
display a table like that

```
COMMAND  PID   USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
node    2091 slucas   21u  IPv4 0x55f00507a74a3aa5      0t0  TCP *:4506 (LISTEN)
```
To kill the process

```
kill -9   2091
```

<script src="https://gist.github.com/sinsunsan/40d5f096ea6aa9f267d64148d4fc1c38">

---
title : Linux tail -f
layout: post
---

tail 명령어 : 파일의 마지막 출력  
tail n [파일명] : 파일을 끝에서 n줄 만큼 출력  
tail -f [파일명] : "follow for". 스트림 유지. 추가된 내용 추가적으로 출력.  


실시간으로 모니터링  
```linux
tail -f [파일명]
```

빠져나올 때는 'Ctrl-C'

---
참고 : [14 tail and head commands in Linux/Unix][1]

[1]: https://www.linux.com/blog/14-tail-and-head-commands-linuxunix
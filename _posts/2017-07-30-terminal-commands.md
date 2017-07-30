---
title: terminal 명령어
date: 2017-07-30 08:50
---

github page 때문이기도 한데, 맥에서 터미널 명령어를 쓸일이 간간히 있음.
맥이 unix 계열 운영체제라 익숙한 dos 명령어와는 차이가 있는데,   
기본적으로는 다르지않은듯, 좀 다른 건 shell 개념인 것 같은데, 이건 좀더 공부가 필요한 것 같음.   
내가 꼭 해야하는 건지 의문이 들기는 하지만... 

재미로 시작한건데, 공부할께 많아서 잘하는 짓인지 좀 의문스럽네   

###명령어 list


`pwd` : path to working directory


`clear` : clear the screen   

`ls` : list files   
`ls -a` : hidden 파일도 보여줌   
`ls -l` : detail information 보여줌, -al로 합쳐서 쓸수 있음.   


`cd` : change directory   
`cd ..` : 이건 익숙하다


`mkdir` : make directory
`touch` : creat an empty file
`cp` : copy   
`cp` [file] [directory]   
`cp -r` [directory] [directory] : directory안의 파일을 다 복사   

`rm` : remove, delete file   
`rm -r` [directory] :directory 통째로 삭제, undo 불가능   

`mv` : move   
`mv` [file] [directory]   
`mv` [file] [file] : 파일 이름 변경으로 사용가능   

`echo` : print out   

`date`: print the date   

 현재 깃허브 페이지 쓰면서 사용하는 명령어는    
```
git add .
```   
```
git commit -m "XXXXX"
```   
``` 
git push origin master
```   
```
git remote show
```   
```
git remote set-url 
```

 





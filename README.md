# opensource_sw_homework_20203247
1. 리눅스 명령어
-  ps  
ps는 process status의 줄인말로 현재 실행중인 프로세스 목록과 상태를 보여준다.    
**ps 사용법**  
  
~~~
ps [option]  
ex) $ ps -ef     <-- -ef 옵션은 모든 프로세스를 풀 포맷으로 출력한다. 
~~~  
  
  **주요 옵션**  

  | 옵션 | 내용 |  
  | --- | --- |  
  |-e|모든 프로세스|  
  |-f|완전한 포맷|  
  |-l|긴 포맷|  
  
이미지 넣고  
  **출력 내용**  
    
||내용|
|---|---|
|UID|실행 유저
|PID|프로세스 ID|
|PPID|부모 프로세스 PIC|
|C|CPU 사용량|
|STIME|Start Time|
|TTY|프로세스 제어 위치  
||-콘솔:tty1|  
||-원격:pts/1|
|TIME|구동 시간|
|CMD|실행 명령어|
   
-  kill
-  jobs    
-  top
2. vim 에디터 매크로 사용법

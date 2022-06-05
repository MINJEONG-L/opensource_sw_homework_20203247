# opensource_sw_homework_20203247
## 1. 리눅스 명령어
### -  ps  
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
  
---
### -  kill  
kill 명령어는 프로세스를 죽일 때 사용하는 명령어로 사용하면 내부적으로 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어이다.  
먼저 ps 명령어를 통해 프로세스들의 pid를 얻고 kill 명령어의 파라미터로 넘겨 실행하면 해당 프로세스를 종료시킬 수 있다.  

**kill 사용법**
  
  ~~~
  kill [options]<pid>
  ex) $kill 1500    <-- pid가 1500인 프로세스를 죽이게 된다.
                        따로 시그널을 지정하지 않았기 때문에 기본 값인 정상 종료(15, SIGTERM)시그널을 보낸다.
  ~~~  
  
  
  ~~~
  시그널 지정 사용법  
  
  kill -s[signal id]<pid>
  kill -s[signal text]<pid>
  kill -[signal id]<pid>
  kill -[signal text]<pid>
  ~~~ 
  
   ** 시그널 종류  
    kill -l 명령어를 통해 사용할 수 있는 시그널을 확인 할 수 있다.
    이미지 넣기  
    
  
---
### -  jobs  
jobs 명령어는 작업의 상태를 표시하는 명령어로 현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력된다.  
즉, 현재 쉘 프로세스의 자식 백그라운드 프로세스들을 보여주는 것이다.  
**jobs 사용법**  
  
~~~
jobs [option][job number]  
ex) $ jobs     <-- option, job number는 선택사항 
~~~  
  
**주요 옵션**  

| 옵션 | 내용 |  
| --- | --- |  
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|  
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|  
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|
  
**출력 내용의 백그라운드 작업 상태값**  
    
|상태|내용|
|---|---|
|Running|작업이 계속 진행중
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 시그널이 작업을 일시 중단|  
  
이미지 넣고  

---
### -  top
2. vim 에디터 매크로 사용법

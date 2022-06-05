# opensource_sw_homework_20203247
## 1. 리눅스 명령어
> ###  ps  
ps는 `process status`의 줄인말로 현재 실행중인 프로세스 목록과 상태를 보여준다.   

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
> ###  kill  
kill 명령어는 프로세스를 죽일 때 사용하는 명령어로 사용하면 내부적으로 프로세스에 `시그널`을 보내 원하는 작업을 하게 하는 명령어이다.  
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
  
  ex) $kill -s SIGTERM 1400
      $kill -15 1400
      $kill -SIGTERM 1400
      $kill -TERM 1500
  ~~~ 
  
   ** 시그널 종류  
    kill -l 명령어를 통해 사용할 수 있는 시그널을 확인 할 수 있다.
    이미지 넣기  
    
  
---
> ###  jobs  
jobs 명령어는 `작업의 상태를 표시`하는 명령어로 현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력된다.  
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
> ###  top  
top 명령어는 현재 OS의 상태를 나타내주는 CLI 어플리케이션이다.  
메모리 사용량, CPU 사용량 등을 나타내주며 top을 실행하는 동안에는 주기적인 업데이트로 실시간에 근접한 내용을 보여준다.  
전체 `요약부분`과 각 프로세스마다 `구체적인 내용`을 포함하는 부분이 있다.  

**top 사용법**  
  
~~~
top 
ex) $ top  
~~~  

이미지  

**전체 요약 영역**  
  
~~~  
요약 영역은 top에서 상단에 위치하며 전체 프로세스가 OS에 대해서 리소스를 어느정도 차지하고 있는지를 알려준다.
대표적인 값은 현재 시간, OS가 살아있는 시간, 현재 접속중인 유저 세션 수, 
로드 에버리지(CPU Load의 이동 평균), Tasks(현재 프로세스들의 상태), CPU 사용량, 메모리 사용량이다.
~~~  
  
**디테일 영역**  
  
~~~  
디테일 영역에는 각 프로세스에 대한 상세한 내용이 나온다.
PID, USER, PR, NI, VIRT, RES, SHR, S, %MEM, TIME+, COMMAND 값이 순서대로 출력된다.
~~~  
  
|상태|내용|
|---|---|
|PID|프로세스 ID|
|USER|프로세스를 실행시킨 사용자 ID|
|PRI|프로세스의 우선순위|
|NI|NICE 값. 일의 nice value값|
|VIRT|가상 메모리의 사용량|
|RES|현재 페이지가 상주하고 있는 크기|
|SHR|분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합|
|S|프로세스의 상태<S(sleeping),R(running), W(swapped out process), Z(zombies)>|
|%CPU|프로세스가 사용하는 CPU의 사용률|
|%MEM|프로세스가 사용하는 메모리의 사용률|
|COMMAND|실행된 명령어|
  
  
  **Top 명령어 옵션**  
    
  ~~~
  top 명령어 실행 중 확인이 가능한 옵션이 있다. (주요 몇가지만 정리)
~~~  
  

  | 옵션 | 내용 |  
  | --- | --- |  
  |shift + p|CPU 사용률이 높은 순서대로 표시|  
  |shift + m|메모리 사용률이 높은 순서대로 표시|  
  |shift + t|프로세스가 돌아가고 있는 시간 순서대로 표시|
  |k| 프로세스 kill -k 입력 후 종료할 PID 입력|
  |a| 메모리 사용랴에 따라 정렬|
  |b|Batch 모드 작동|
    
    
## 2. vim 에디터 매크로 사용법  
> vim 에디터로 매크로 Recording 하기
  
  
```mermaid
graph LR
A(커맨드모드 ESC)-->B(q 누르기)  
B-->C(a와 z사이 문자로 recording 시작)   
C-->D(커맨드모드 ESC)  
D-->E(q 누르기 recording 끝) 
```
  
> 매크로 사용하기  
```
  1. ESC를 눌러 커맨드 모드로 돌아온다.
  2. @ + recording 시작할 때 눌렀던 문자
``` 

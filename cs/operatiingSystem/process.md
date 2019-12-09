## 프로세스란..?

- 실행중인 프로그램을 의미한다.
- 스케줄링의 대상이 되는 작업(task)과 같은 의미로 쓰인다.
> 사실을 하나의 프로세스당 최소 하나 이상의 스레드가 있는데, 실제로는 스레드 단위로 스케줄링을 한다.
- 프로세스 하나당 하나의 메모리 구조를 가집니다.(code, data, heap, stack영역)

#### 프로세스 배경지식

실제 디스크에 있는 프로그램을 실행하게 되면,
실행을 하기 위해 해당 프로그램은 메모리 할당이 이루어지고, 
할당된 공간으로 바이너리 코드가 올라가게 되는데(메모리에 적재됨)
이 순간부터 프로세스라 부른다.

#### 메모리 구조
	•	Code 영역: 프로그램을 실행시키는 실행 파일 내의 명령어들(소스코드)이 올라갑니다.
	•	Data 영역: 전역변수, static 변수들 할당
	•	Heap 영역: 동적할당 공간
	•	Stack 영역: 지역변수, 파라미터(메소드 인자값들)를 위한 메모리 영역

#### 프로세스 스케줄링

CPU 하나당 동시에 실행되야 할 프로그램(프로세스)가 여러개이면 어떻게 될까??
-> 여러 프로세스들을 고속으로 순서를 정해서(우선순위) 하나하나 실행한다!

즉, 스케쥴링이란
CPU 할당 순서 및 방법을 결정하는 일

#### 프로세스 상태변화

프로세스 상태변화는 크게 ready, blocked, running 상태가 있어요.

	•	Ready: 프로세스가 생성되면 프로세스는 ready Queue에 올라가게 됩니다.
	•	Running Read Queue에 있던 프로세스들이 스케쥴링에 의해 실행되어야 할 프로세스가 CPU에 할당되면서 Running 상태가 됩니다.
	⁃	-> Ready: 실행중인 프로그램A보다 Queue에 있던 프로세스B가 우선순위가 더 높다면 실행중이던 A는 다시 ReadyQueue로 들어가게 됩니다.
	⁃	-> Blocked: 실행중이던 프로세스A에서 입출력 이벤트 발생시 프로세스A는 Blocked 상태로 됩니다.
	⁃	Block -> ready: 입출력 이벤트가 끝나면 다시 Ready상태가 됩니다.
	⁃	-> Terminate: 프로세스 종료

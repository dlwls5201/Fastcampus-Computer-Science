## 프로세스와 스케줄러의 이해 - 컨텍스트 스위칭

## PCB

컨텍스트 스위치잉 일어날 때 Process Control Block에 PC, SP를 저장합니다.

1. Process ID
2. Register 값 (PC, SP 등)
3. Scheduling Info (Process State)
4. Memory Info

등등의 정보를 가지고 있음.

## Context Switching (문맥 교환)
- CPU에 실행할 프로세스를 교체하는 기술
- 프로세스 상태 정보를 PCB로부터 CPU에 로드하고 실행

1. 실행 중지할 프로세스 정보를 해당 프로세스의 PCB에 업데이트해서, 메인 메모리에 저장
2. 다음 실행할 프로세스 정보를 메인 메모리에 있는 해당 PCB 정보(PC,SP)를 CPU에 넣고 실행

> 디스패치 (dispatch): ready 상태의 프로세스를 running 상태로 바꾸는 것

## 여기서 잠깐 - 컴파일러
- CPU 아키텍처에 따라서는 컴파일러는 프로그램만 만들면 됨, 기존 코드는 재상성할 필요 없음 (이식성 UP)
- 그러나, 어셈블리어로 작성한 코드보다는 속도가 떨어질 수 있음



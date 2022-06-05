# 오픈소스SW 과제2, 학번 20205089, 이름 김형준

## 1. 리눅스 명령어

### 1. top 명령어
- **시스템의 상태를 전반적으로 가장 빠르게 파악 가능 (CPU, Memory, Process)**
- **옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌**
- **top 실행 전 옵션**
 1. 순간의 정보를 확인하려면 –b 옵션 추가(batch 모드)
 2. -n : top 실행 주기 설정(반복 횟수)
- **top 실행 후 명령어**
 1. shift + p : CPU 사용률 내림차순
 2. shit + m : 메모리 사용률 내림차순
 3. shift + t : 프로세스가 돌아가고 있는 시간 순
 4. k : kill. k 입력 후 PID 번호 작성. signal은 9
 5. k : kill. k 입력 후 PID 번호 작성. signal은 9
 6. a : 메모리 사용량에 따라 정렬
 7. b : Batch 모드로 작동
 8. 1 : CPU Core별로 사용량 보여줌
- **ps와 top의 차이점**
 1. ps는 ps한 시점에 proc에서 검색한 cpu 사용량
 2. top은 proc에서 일정 주기로 합산해 cpu 사용율 출력
- **top –b –n 1**

!<img src="https://user-images.githubusercontent.com/106909588/172050535-e494437f-6845-45c6-892f-b7a50d0700eb.png" width="640" height="480">

 1. 0 : 0분전에 서버가 구동
 2. load average : 현재 시스템이 얼마나 일을 하는지를 나타냄. 3개의 숫자는 1분, 5분, 15분 간의 평균 실행/대기 중인 프로세스의 수. CPU 코어수 보다 적으면 문제 없음
 3. Tasks : 프로세스 개수
 4. KiB Mem, Swap : 각 메모리의 사용량
 5. PR : 실행 우선순위
 6. VIRT, RES, SHR : 메모리 사용량 => 누수 check 가능
 7. S : 프로세스 상태(작업중, I/O 대기, 유휴 상태 등)

- **VIRT, RES, SHR**
 1. VIRT
  - 프로세스가 사용하고 있는 virtual memory의 전체 용량
  - 프로세스에 할당된 가상 메모리 전체
  - SWAP + RES
 2. RES
  - 현재 프로세스가 사용하고 있는 물리 메모리의 양
  - 실제로 메모리에 올려서 사용하고 있는 물리 메모리
  - 실제로 메모리를 쓰고 있는 RES가 핵심!
 3. SHR
  - 다른 프로세스와 공유하고 있는 shared memory의 양
  - 예시로 라이브러리를 들 수 있음, 대부분의 리눅스 프로세스는 glibc라는 라이브러리를 참고하기에 이런 라이브러리를 공유 메모리에 올려서 사용
- **Memory Commit**
 1. 프로세스가 커널에게 필요한 메모리를 요청하면 커널은 프로세스에 메모리 영역을 주고 실제로 할당은 하지 않지만 해당 영역을 프로세스에게 주었다는 것을 저장해둠
 2. 이런 과정을 Memory commit이라 부름
 3. 왜 커널은 프로세스의 메모리 요청에 따라 즉시 할당하지 않고 Memory Commit과 같은 기술을 사용해 요청을 지연시킬까?
  - fork()와 같은 새로운 프로세스를 만들기 위한 콜을 처리해야 하기 때문
  - fork() 시스템 콜을 사용하면 커널은 실행중인 프로세스와 똑같은 프로세스를 하나 더 만들고, exec() 시스템 콜을 통해 다른 프로세스로 변함. 이 때 확보한 메모리가 쓸모               없어질 수 있음
  - COW(Copy-On-Write) 기법을 통해 복사된 메모리 영역에 실제 쓰기 작업이 발생한 후 실질적인 메모리 할당을 진행
- **프로세스 상태**
 1. SHR 옆에 있는 S 항목으로 볼 수 있음
  - D : Uninterruptiable sleep. 디스크 혹은 네트워크 I/O를 대기
  - R : 실행 중(CPU 자원을 소모)
  - S : Sleeping 상태, 요청한 리소스를 즉시 사용 가능
  - T : Traced or Stopped. 보통의 시스템에서 자주 볼 수 없는 상태
  - Z : zombie. 부모 프로세스가 죽은 자식 프로세스



### 2. ps 명령어

### 3. jobs 명령어

### 4. kill 명령어

## 2. vim 에디터 매크로 사용방법

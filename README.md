# 오픈소스SW 과제2, 학번 20205089, 이름 김형준

## 1. 리눅스 명령어

### 1. top 명령어
- 시스템의 상태를 전반적으로 가장 빠르게 파악 가능 (CPU, Memory, Process)
- 옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌
- top 실행 전 옵션
 1. 순간의 정보를 확인하려면 –b 옵션 추가(batch 모드)
 2. -n : top 실행 주기 설정(반복 횟수)
-top 실행 후 명령어
 1. shift + p : CPU 사용률 내림차순
 2. shit + m : 메모리 사용률 내림차순
 3. shift + t : 프로세스가 돌아가고 있는 시간 순
 4. k : kill. k 입력 후 PID 번호 작성. signal은 9
 5. k : kill. k 입력 후 PID 번호 작성. signal은 9
 6. a : 메모리 사용량에 따라 정렬
 7. b : Batch 모드로 작동
 8. 1 : CPU Core별로 사용량 보여줌
-ps와 top의 차이점
 1. ps는 ps한 시점에 proc에서 검색한 cpu 사용량
 2. top은 proc에서 일정 주기로 합산해 cpu 사용율 출력
- top –b –n 1
### 2. ps 명령어

### 3. jobs 명령어

### 4. kill 명령어

## 2. vim 에디터 매크로 사용방법

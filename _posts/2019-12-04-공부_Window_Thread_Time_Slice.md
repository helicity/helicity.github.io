## windows process/thread context time slice

https://superuser.com/questions/1326252/changing-windows-thread-sheduler-timeslice

time slice = quantum

client SKU = 20ms (normal), 60ms (owns foreground windows)
server SKU = 120ms

새 회사 업무회의 중에 쓰레드 갯수를 4개로 돌리고 있다는 (물리 프로세서 갯수와 동일) 얘기를 듣고
확인차 다시 찾아본 것인데, 쓰레드 갯수를 더 늘리는 것이 유리한 점은 여전히 유효하다.


2n+1 공식에 관한 문헌은 찾기 어려우나, (IOCP 이용하는 윈도우 네트웍 교재 등에서 나와있는 얘기인 듯 하다.
이 경우는 blocking 과 waiting이 빈번하게 발생하므로 2n+1은 이론적으로도 상당히 설득력을 가지게 된다.)
아래에 어떤 자가 벤치마크 프로그램으로 실험한 내용이 적혀있다.
이 결과에 다르면 로지컬 코어 개수만큼 쓰레드 생성시 가장 효율적이었다고.
https://medium.com/data-design/destroying-the-myth-of-number-of-threads-number-of-physical-cores-762ad3919880

## Async
> Excel 생성 모듈을 짜면서 공부했던 것들을 돌아보며

### Async
 * Async 는 사실 별거 없다. 운영체제 수업때 들었던 것들이 그대로 있다.
    * 운영체제에서 오래 걸리는 I/O 시 Process 는 WAIT 상태가 된다.
    * WAIT 상태인 Process 는 I/O Interrupt 가 들어오기 전까지 쭉 대기한다.
    * 그리고 지금 돌릴 수 있는 다른 것들을 scheduler 의 정책에 맞게 선택해서 돌린다.

 * 그렇다면 Async web 은?
   * Task queue 에 있는 것을 Thread pool 이 열심히 돌린다.
   * Thread pool 은 scheduler 가 되는 것이고
   * Thread 는 CPU 와 같은 자원이다.

결국 동작 자체는 운영체제의 scheduler 와 비동기 웹 서비스는 비슷하다.

### 장단점

 * 운영체제에서의 Async 와 web 에서의 async 의 최종목표는 같은 것 같다.
   * 더 적은 Resource 로도 더 많은 throughput 을 !
   * 운영체제나 웹이나 마찬가지지만 기존의 방법에 비해 오버헤드 (Context switching 이 대표적) 가 있는 방법이다.
   * 그래서 Latency 는 대부분의 경우에 좋아지고, Throughput 은 프로세스 수(요청 수)에 따라 다르지만 프로세스(요청)가 많을 경우 throughput 도 좋아진다.

## 비동기로 짤 때 주의할 점

##            
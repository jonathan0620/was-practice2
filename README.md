• Step1 - 사용자 요청을 메인 Thread가 처리하도록 한다.

• Step2 - 사용자 요청이 들어올 때마다 Thread를 새로 생성해서 사용자 요청을 처리하도록 한다.

• Step3 - Thread Pool을 적용해 안정적인 서비스가 가능하도록 한다


[Step1] - 사용자 요청을 메인 Thread가 처리하도록 한다.

![image](https://github.com/jonathan0620/was-practice2/assets/145638699/b0f5358b-304f-46ba-bc07-56e8a3fecc2a)

--> 계산기 프로그램 실행 모습

![image](https://github.com/jonathan0620/was-practice2/assets/145638699/7fffae87-b688-462b-ad48-5ac483b4fe0f)

--> 서버 연결 모습


[Step2] - 사용자 요청이 들어올 때마다 Thread를 새로 생성해서 사용자 요청을 처리하도록 한다.

ㄴ 스레드를 이미 고정된 개수만큼 생성해두고 이를 재활용하는 스레드 풀 개념을 적용해서 안정적인 서비스가 가능하도록 함.
![image](https://github.com/jonathan0620/was-practice2/assets/145638699/ea75ef28-aae2-4f2a-a722-cde1f6b0ec9b)
--> Thread 연결 모습 


메모리 할당 작업은 상당히 비싼 작업,
따라서 사용자 요청이 있을 때마다 thread를 생성하게 된다면 성능이 떨어짐.
동시 접속자 수가 많아질 경우 많은 쓰레드가 생성되는데 많아지면 cpu context swithching 횟수와 cpu와 메모리 사용량이 증가함.
따라서 최악의 경우 서버의 리소스 한계로 인해 서버가 다운될 수 있음
이러한 이유 때문에 thread Pool을 적용해 안정적인 서비스가 가능하도록 구현.

[Step3] - Thread Pool을 적용해 안정적인 서비스가 가능하도록 한다

![image](https://github.com/jonathan0620/was-practice2/assets/145638699/d6cef12a-119f-4684-b50c-8c36f316be29)
--> poo1 thread1 (poo1에서 꺼낸 thread임을 확인 가능)

# Big O

big O 자체는 알고리즘의 효율성을 표시하는 language다.
알고리즘의 표기는 Asymptotic Notation이라 해서 점근적 표기법을 사용한다.
주어진 데이터 크기를 기준으로 시간, 공간을 이용해 지표를 제시한다.

- O(big O)

  - academic하게 보면 big O는 upper bound on the time이라 해서 상한을 의미한다.
  - 새로 만든 알고리즘이 기존보다 같거나 좋음을 의미
  - 예를 들어, 알고리즘의 수행 시간은 매 시간 달라지는데 그 중 가장 나쁜 값을 정하고 그걸 기준점으로 파악한다.

- big Omega

  - big O와 비슷하나 lower bound라 해서 하한을 의미
  - 새로 만든 알고리즘이 기존보다 같거나 별로임을 의미

- big theta
  - theta는 O, omega 둘 모두를 포함한다. tight bound on the runtime
  - 즉, 새로 만든 알고리즘은 기존의 범위 안에 존재함을 의미

quick sort의 예시

- quick sort는 랜덤으로 pivot 요소를 고르고, pivot보다 작은
- 가장 좋은 경우

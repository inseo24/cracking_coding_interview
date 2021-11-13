# Big O

big O 자체는 알고리즘의 효율성을 표시하는 language다.
알고리즘의 표기는 Asymptotic Notation이라 해서 점근적 표기법을 사용한다.
주어진 데이터 크기를 기준으로 시간, 공간을 이용해 지표를 제시한다.

## 시간 복잡도(Time Complexity)

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

- quick sort는 랜덤으로 pivot 요소를 고르고, pivot보다 작은 요소가 pivot 보다 큰 요소 앞에 나타나도록 배열의 값을 바꾼다. 일종의 부분 정렬이다. 그리고 비슷한 프로세스로 왼쪽과 오른쪽을 재귀적으로 정렬한다.
  - Best case
    - 모든 요소가 같다면 quick sort는 평균적으로 배열을 한 번만 통과한다.
      이게 O(N)이다.
  - Worst case
    - 운이 나쁘게 pivot이 반복적으로 배열에서 가장 큰 값이라면? 이 경우, 재귀로 배열을 반으로 나눌 수 없고 그냥 단순히 하위 배열을 한 요소만큼 줄일 것이다. 이건 O(N^2) 으로 떨어진다.
  - Expected Case
    - 일반적으로 best case나 worst case는 잘 생기지 않는다. pivot이 너무 낮거나 너무 높을 때가 있을 수 있으나 보통 그렇지 않고 대부분 예상하면 O(N log N) 정도 된다.

best, worst, expected case 와 big O, bit Omega, big theta가 관계가 있는 건 아니다.
단지 이런 case들이 특정 input에 의해 big O time으로 표현될 뿐이다.

## 공간 복잡도(Space Complexity)

시간뿐만 아니라 알고리즘에 요구되는 메모리의 양을 고려해야 한다.
공간 복잡도는 시간 복잡도에 평행되는 개념이다. 우리가 size가 n인 array를 생성하고 싶으면, 이건 O(n)의 공간이 필요하다. 만약 nxn의 다차원 배열을 생성하고 싶다면 O(n^2)의 공간이 필요하다.

재귀 호출이 있는 stack의 공간도 똑같이 count된다. 예를 들어, 아래 코드는 O(n)의 시간과 O(n)의 공간을 갖는다.

```java
int (n <= 0) {
  if (n <= 0) {
    return 0;
  }
  return n + sum(n-1);
}
```

각각의 호출은 stack에 level을 추가한다.

```
sum(4) -> sum(3) -> sum(2) ... -> sum(0)
```

각 호출들이 call stack에 쌓여서 실제 메모리를 차지한다.
n번 호출한다고 꼭 O(n) 공간을 차지하는 건 아니다.

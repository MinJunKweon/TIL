# Boyer–Moore majority vote algorithm

[Wikipedia](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_majority_vote_algorithm)

> N개의 정수 Array에서 과반수(`N/2`번)보다 많이 출현한 정수를 찾는 알고리즘
>
> 시간복잡도 : `O(N)`, 공간복잡도 : `O(1)`

### 컨셉

```
Majority Element의 출현 횟수 > 다른 Elements들의 출현횟수
```

위 전제조건을 만족하는 상황에서 배열을 처음부터 순회할 때, 순회하는 각 시점기준으로 가장 많이 출현한 Majority Element와 그 횟수를 기록해둔다.

가장 마지막까지 순회했을 때, 기록되어있는 Majority Element가 배열에서 과반수로 나온 정수임을 알 수 있다.

(단, 위 조건을 만족하지 않는 경우 값을 찾을 수 없다.)

### 로직

![image-20210128204819069](C:\Users\Minz\AppData\Roaming\Typora\typora-user-images\image-20210128204819069.png)

1. `majority`, `appear_count` 변수 선언
   * `majority` : 과반수로 많이 출현한 정수
   * `appear_count` : `majority`의 출현 횟수
2. 배열 순회 (N번째 element까지 각 element를 `e` 라고 호칭)
3. `majority`와 `e`가 같은가?
   * 같다 : `appear_count` 1 증가 
   * 다르다 : `appear_count` 1 감소
4. `appear_count`가 음수라면?
   * `majority`를 `e`로 변경
   * `appear_count`를 1로 변경

## 연관문제

* [LeetCode - 169번 문제](https://leetcode.com/problems/majority-element/) - Easy
* [LeetCode - 229번 문제 (심화)](https://leetcode.com/problems/majority-element-ii/) - Medium
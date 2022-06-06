---
title:  "Recursion"
excerpt: "Data_Structure - Recursion"

categories:
  - Data_Structure
tags:
  - Data_Structure
  - Recursion
  
---

***
**재귀(recursion)**
======

어려운 문제를 단순화하는데 주로 사용한다. 

문제를 동일한 구조의 더 작은 문제로 나누고, 
작은 문제를 해결함으로써 전체 문제를 해결하는 방법 

재귀를 적용한 코드는 간결하고 이해하기 쉽다. 
실행 과정 중 자기 자신을 호출하는 것을 재귀 호출이라고 한다. 

모든 재귀 함수는 반복문(while 문 또는 for 문)으로 표현이 가능하다. 

***

-  재귀 사용 예시


1. 주어진 문제를 비슷한 구조의 더 작은 문제로 나눌 수 있는 경우
2. 중첩된 반복문이 많거나 반복문의 중첩 횟수를 예측하기 어려운 경우
3. 변수 사용을 줄여 mutable state (변경 가능한 상태) 를 제거하여 
   프로그램 오류가 발생할 수 있는 가능성을 줄이는 경우

```java
for(int i = 0; i < n; i++) {
	for(int j = 0; j < n; j++) {
		for(int k = 0; k < n; k++) {
			for(int l = 0; l < n; l++) {
				for(int m = 0; m < n; m++) {
					Func(i, j, k, l, m);
				}
			}
		}
	}
}
```

- 팩토리얼

```java
f(n) = n x f(n-1) // n>=1
        1          // n = 0

  if(n==0)
	return 1;
    else 
	return n * Factorial(n-1);
```

***

- 재귀함수 작성 

1. 재귀 함수의 입력값과 출력값 정의하기
: 재귀 함수를 통해 풀고자 하는 문제의 목표를 정의 
  (문제를 추상적 or 단순하게 정의 )

2. 문제를 쪼개고 경우의 수를 나누기
문제를 쪼갤 기준에 따라 문제를 더 큰 경우와 작은 경우로 구분할 수 있는지 확인
(일반적으로는 입력값으로 기준 정함
-> 문제를 더 이상 쪼갤 수 없는 경우와 그렇지 않은 경우로 나눔)

3. 단순한 문제 해결하기
재귀의 기초 : 가장 해결하기 쉬운 문제부터 해결, 재귀 함수를 구현할 때, 재귀의 탈출 조건(재귀 호출이 멈추는 조건)을 구성

4. 복잡한 문제 해결하기
: 남아있는 복잡한 경우를 해결

5. 코드 구현

**! ) 입력값이나 문제의 순서와 크기 고려**
: 주어진 입력값 또는 문제 상황을 크기나 순서로 구분
  문제를 푸는 방식이 순서나 크기에 관계없이 모두 같아야 함

***

- 재귀함수 탬플릿 예시

```java
public type recursive(input1, input2, ...) {
  // Base Case : 문제를 더 이상 쪼갤 수 없는 경우
  if (문제를 더 이상 쪼갤 수 없을 경우) {
    return 단순한 문제의 해답;
  }
  // recursive Case
  // 그렇지 않은 경우
  return 더 작은 문제로 새롭게 정의된 문제
  // 예1. someValue + recursive(input1Changed, input2Changed, ...)
  // 예2. someValue * recursive(input1Changed, input2Changed, ...)
}
```

***

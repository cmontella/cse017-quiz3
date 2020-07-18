# CSE017 - Quiz 3

Remember, make at least 1 commit per question. Minimum of 4 commits for this assignment. You may commit directly to this file for your answers.

## Question 1 

Write down a UML model for a doubly linked list node. You don't have to implement this in Java.

## Question 2

Convert the following function from to an equivalent recursive form:

```java
int sum(int[] list) {
  int current_sum = 0;
  for (int i = 0; i < list.length; i++) {
    current_sum += list[i];
  }
  return current_sum;
}
```

## Question 3

Convert the following function from to an equivalent recursive form:

```java
int max(int[] list) {
  int current_max = 0;
  for (int i = 0; i < list.length; i++) {
    if (list[i] > current_max) {
      current_max = list[i];
    }
  } 
  return current_max;
}
```

## Question 4

Convert the following function from to an equivalent recursive form:

```java
int gcd(int a, int b) {
  while (a != b) {
    if (a > b) {
      a -= b;
    } else if (b > a) {
      b -= a;
    }
  }
}
```

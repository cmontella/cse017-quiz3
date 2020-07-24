# CSE017 - Quiz 3

Remember, make at least 1 commit per question. Minimum of 4 commits for this assignment. You may commit directly to this file for your answers.

## Question 1 

Write down a UML model for a doubly linked list node. You don't have to implement this in Java.

```
Class name: Node
Attributes:
- int item
- Node previous
- Node next
Methods
+ Node(int item)
+ Node(int item, Node next)
+ Node(int item, Node next, Node previous)
+ void setItem(int item)
+ int getItem()
+ void setNext(Node next)
+ Node getNext()
+ void setPrevious(Node next)
+ Node getPrevious()
```

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
**Solution:**

I use the following method to help with Q2 and Q3. You don't need this if you use ArrayList and use the subList() method.

```java
public static int[] tail(int[] array) {
  int[] tail = new int[array.length - 1];
  for (int i = 1; i < array.length; i++) {
    tail[i-1] = array[i];
  }
  return tail;
}
```
```
public static int sum_recursive(int[] list) {
  if (list.length == 1) {
    // Base case 
    return list[0];        
  } else {
    int head = list[0];
    int[] tail = tail(list);
    // Recursive Step
    return head + sum_recursive(tail);              
  }
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

**Solution:**

```java
public static int max_recursive(int[] list) {
  if (list.length == 1) {
    return list[0];
  } else {
    int head = list[0];
    int[] tail = tail(list);
    int tail_max = max_recursive(tail);
    if (tail_max > head) {
      return tail_max;
    } else {
      return head;
    }
  }
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
**Solution:**

```java
int gcd(int a, int b) {
  if (a==b) {
    return a;
  } else if (a>b) {
    return gcd((a-b), b);
  } else {
    return gcd(a, (b-a));
  }
}
```


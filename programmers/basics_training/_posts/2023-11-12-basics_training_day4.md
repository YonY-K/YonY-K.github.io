---
title: "Day 4 연산, 조건문"
tag: basics_training
---

### n의 배수
![n의 배수](https://github.com/yony-k/yony-k.github.io/assets/109204976/b76b6518-9b85-4aa7-a51d-dba1cde28697)

```java
class Solution {
    public int solution(int num, int n) {
        int answer = 0;
        
        answer = num%n==0 ? 1 : 0;
        
        return answer;
    }
}
```

---

### 공배수
![공배수](https://github.com/yony-k/yony-k.github.io/assets/109204976/6001b996-35c2-4de7-9fc8-06e31246a8ab)

```java
class Solution {
    public int solution(int number, int n, int m) {
        int answer = 0;
        if(number%n==0&&number%m==0) answer=1;
        else answer=0;

        //answer = number%n==0&&number%m==0 ? 1 : 0;
        return answer;
    }
}
```

---

### 홀짝에 따라 다른 값 반환하기
![홀짝에 따라 다른 값 반환하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/c865398d-7f07-46e4-bab7-1d58d2021a84)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        if(n%2!=0) {
            for(int i=n;i>0;i--) {
                if(i%2!=0) answer += i;
            }
        } else {
            for(int i=n;i>0;i--) {
                if(i%2==0) answer += Math.pow(i,2);
            }
        }
        return answer;
    }
}
```

---

### 조건 문자열
![조건 문자열](https://github.com/yony-k/yony-k.github.io/assets/109204976/f18e8f6e-e6c1-4963-892e-a1f5f4bdad16)

```java
class Solution {
    public int solution(String ineq, String eq, int n, int m) {
        int answer = 0;
        
        if(ineq.equals("<")) {
            answer = eq.equals("=")? (n<=m?1:0) : (n<m?1:0);
        } else {
            answer = eq.equals("=")? (n>=m?1:0) : (n>m?1:0);
        }
        
        return answer;
    }
}
```

---

### flag에 따라 다른 값 반환하기
![flag에 따라 다른 값 반환하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/cca2577f-dc39-41ef-8d9d-fb527de593e9)

```java
class Solution {
    public int solution(int a, int b, boolean flag) {
        int answer = 0;
        return answer = flag? a+b : a-b;
    }
}
```


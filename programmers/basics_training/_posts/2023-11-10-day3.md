---
title: "Day 3 출력"
tag: basics_training
---

### 문자열 섞기
![문자열 섞기](https://github.com/yony-k/yony-k.github.io/assets/109204976/85586542-b2f8-49dc-af8c-ebef5b2c29e6)

```java
class Solution {
    public String solution(String str1, String str2) {
        String answer = "";
        
        for(int i=0;i<str1.length();i++){
            answer += str1.charAt(i);
            answer += str2.charAt(i);
        }
        
        return answer;
    }
}
```

---
### 문자 리스트를 문자열로 변환하기 
![문자 리스트를 문자열로 변환하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/233ee473-022c-42c8-a8fe-c8a1cdfa3d14)

```java
class Solution {
    public String solution(String[] arr) {
        String answer = "";
        for(int i=0;i<arr.length;i++) {
            answer += arr[i];
        }
        return answer;
    }
}
```

---
### 문자열 곱하기
![문자열 곱하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/868bcfdb-8912-49b3-a1a3-9fd8d8863780)

```java
class Solution {
    public String solution(String my_string, int k) {
        String answer = "";
        for(int i =0;i<k;i++){
            answer += my_string;
        }
        return answer;
    }
}
```

---
### 더 크게 합치기
![더 크게 합치기](https://github.com/yony-k/yony-k.github.io/assets/109204976/1292318a-e410-4956-9c27-c2ffea2249a2)

```java
class Solution {
    public int solution(int a, int b) {
        int answer = 0;
        int s1 = Integer.parseInt(a+""+b);
        int s2 = Integer.parseInt(b+""+a);
        
        if(s1>s2) answer = s1;
        else answer = s2;
        
        return answer;

        //return answer = s1>s2 ? s1 : s2;
    }
}
```

---
### 두 수의 연산값 비교하기
![두 수의 연산값 비교하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/beb0ba99-a8f4-4fda-92b3-41b4e9ea564a)

```java
class Solution {
    public int solution(int a, int b) {
        int answer = 0;
        int n = Integer.parseInt(a+""+b);
        int m = 2*a*b;
        
        if(n>m) answer = n;
        else if(n<m) answer = m;
        else answer = n;
        
        return answer;
    }
}
```

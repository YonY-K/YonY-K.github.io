---
title: "문자열, 조건문, 수학, 반복문"
tag: beginner
---

### 특정 문자 제거하기
![특정 문자 제거하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/c75dc25f-8f7e-4594-ae8a-671fe55fa8e4)

```java
class Solution {
    public String solution(String my_string, String letter) {
        String answer = "";
        
        answer = my_string.replaceAll(letter, "");
        
        return answer;
    }
}
```

---

### 각도기
![각도기](https://github.com/yony-k/yony-k.github.io/assets/109204976/e5ae1f1e-6624-4346-8997-d31d91d3de48)

```java
class Solution {
    public int solution(int angle) {
        int answer = 0;
        
        if(angle < 90) answer = 1;
		else if(angle==90) answer = 2;
		else if(angle<180) answer = 3;
		else answer =4;
        
        return answer;
    }
}
```

---

### 양꼬치
![양꼬치](https://github.com/yony-k/yony-k.github.io/assets/109204976/28ec3203-cb1a-4e69-9046-37f775bff745)

```java
class Solution {
    public int solution(int n, int k) {
        int answer = 0;
        
        k-=n/10;
		
		answer = (n*12000)+(k*2000);
        
        return answer;
    }
}
```

---

### 짝수의 합
![짝수의 합](https://github.com/yony-k/yony-k.github.io/assets/109204976/3a5c201a-56dc-4fdd-b43b-a10d45ad167b)

```java
import java.util.stream.*;

class Solution {
    public int solution(int n) {
        int answer = 0;
        
        answer = IntStream.rangeClosed(1, n).filter(i->i%2==0).sum();
        
        return answer;
    }
}
```


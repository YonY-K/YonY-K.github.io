---
title: "수학, 배열"
tag: beginner
---

### 피자 나눠 먹기 (1)
![피자 나눠 먹기 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/a12685c4-60c7-4828-8ebc-11694f851647)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        if(n%7==0) answer = n/7;
		else if((n%7)<0) answer = 1;
		else answer = n/7+1;
        
        return answer;
    }
}
```

---

### 피자 나눠 먹기 (2)
![피자 나눠 먹기 (2)](https://github.com/yony-k/yony-k.github.io/assets/109204976/11ca744d-c734-41c7-b4a5-9d0d510c10fb)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        int p =6;
		
		while(p%n!=0) {
			p+=6;
		}
		
		answer = p/6;
        
        return answer;
    }
}
```

---

### 피자 나눠 먹기 (3)
![피자 나눠 먹기 (3)](https://github.com/yony-k/yony-k.github.io/assets/109204976/2cb95232-cb9a-4398-8bbe-b5c50463a3ec)

```java
class Solution {
    public int solution(int slice, int n) {
        int answer = 0;
        
        answer = n%slice==0? n/slice : n/slice+1;
        return answer;
    }
}
```

---

### 배열의 평균값
![배열의 평균값](https://github.com/yony-k/yony-k.github.io/assets/109204976/4a3c4a9b-c6a7-4058-a9cd-2a8dd87b1a32)

```java
class Solution {
    public double solution(int[] numbers) {
        double answer = 0;
        
        for(int a : numbers) {
			answer+=a;
		}
		
		answer /= numbers.length;
        
        return answer;
    }
}
```


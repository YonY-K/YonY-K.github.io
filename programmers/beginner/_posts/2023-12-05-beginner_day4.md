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
- 사람수/피자조각 으로 나눠주면 필요한 피자의 개수를 알 수 있다.
- 단 나머지가 남는 경우는 1을 더해준다.

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

- 모두 같은 수의 피자 조각을 먹어야한다는 소리는 사람이 먹는 피자의 수와 피자 조각의 수가 같아질 때를 찾아야한다는 소리다.

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

- 1번 문제와 비슷한데 이번에는 피자조각이 정해져있지 않다는 소리다.
- 풀이는 똑같다.

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
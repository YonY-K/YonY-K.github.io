---
title: "조건문, 반복문, 시뮬레이션, 문자열"
tag: beginner
---

### 가까운 수
![가까운 수](https://github.com/yony-k/yony-k.github.io/assets/109204976/be28021e-cf04-46d4-94c1-0b6bd8852523)

```java
class Solution {
    public int solution(int[] array, int n) {
        int answer = 0;
        
        int[] find = new int[2];
		find[0] = Integer.MAX_VALUE;
		
		for(int i=0;i<array.length;i++) {
			int tmp = Math.abs(n-array[i]);
			if(find[0]>tmp) {
				find[0]=tmp;
				find[1]=array[i];
			} else if(find[0]==tmp) {
				if(find[1]>array[i]) find[1]=array[i];
			}
		}
        
        return answer=find[1];
    }
}
```

---

### 369게임
![369게임](https://github.com/yony-k/yony-k.github.io/assets/109204976/fb7d59e1-f623-4836-9466-e096831cbda8)

```java
import java.util.stream.*;

class Solution {
    public int solution(int order) {
        int answer = 0;
        
        long n = String.valueOf(order).chars().filter(i->i=='3'||i=='6'||i=='9').count();
        
        return answer=(int)n;
    }
}
```

---

### 암호 해독
![암호 해독](https://github.com/yony-k/yony-k.github.io/assets/109204976/6c9b2b30-4715-454e-9381-b0c4e55a4c9b)

```java
class Solution {
    public String solution(String cipher, int code) {
        String answer = "";
        
        for(int i=code-1;i<cipher.length();i+=code) {
			answer += cipher.charAt(i);
		}
        
        return answer;
    }
}
```

---

### 대문자와 소문자
![대문자와 소문자](https://github.com/yony-k/yony-k.github.io/assets/109204976/dc8b5f50-ccb7-4fe7-9831-6eb222466539)

```java
class Solution {
    public String solution(String my_string) {
        String answer = "";
        
        for(int i=0;i<my_string.length();i++) {
			char ch = my_string.charAt(i);
			if(ch>='A'&&ch<='Z') answer += (char)(ch+32);
			else answer += (char)(ch-32);
		}
        
        return answer;
    }
}
```


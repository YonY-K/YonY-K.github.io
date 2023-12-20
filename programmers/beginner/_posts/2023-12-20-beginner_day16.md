---
title: "문자열, 수학, 배열, 조건문"
tag: beginner
---

### 편지
![편지](https://github.com/yony-k/yony-k.github.io/assets/109204976/19951e31-e1ad-49af-ad3b-fa40be0e6578)

```java
class Solution {
    public int solution(String message) {
        int answer = 0;
        
        answer = message.length()*2;
        
        return answer;
    }
}
```

---

### 가장 큰 수 찾기
![가장 큰 수 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/03e8893d-b636-4744-b1aa-51bf622050d5)

```java
class Solution {
    public int[] solution(int[] array) {
        int[] answer = new int[2];
            
        answer[0] = Integer.MIN_VALUE;
		
		for(int i=0;i<array.length;i++) {
			if(answer[0]<array[i]) {
				answer[0]=array[i];
				answer[1]=i;
			}
		}
            
        return answer;
    }
}
```

---

### 문자열 계산하기
![문자열 계산하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/68f706b8-77a9-4097-be4e-709ade1d3a4d)

```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        
        String[] sp = my_string.split(" ");
		
		for(int i=0;i<sp.length;) {
			if(sp[i].equals("+")) {
				if(i==1) answer += Integer.parseInt(sp[i-1])+Integer.parseInt(sp[i+1]);
				else answer += Integer.parseInt(sp[i+1]);
				i+=2;
			} else if(sp[i].equals("-")) {
				if(i==1) answer += Integer.parseInt(sp[i-1])-Integer.parseInt(sp[i+1]);
				else answer -= Integer.parseInt(sp[i+1]);
				i+=2;
			} else {
				i++;
				continue;
			}
		}
        
        return answer;
    }
}
```

---

### 배열의 유사도
![배열의 유사도](https://github.com/yony-k/yony-k.github.io/assets/109204976/41a31354-813e-4554-9316-6dbc63904253)

```java
import java.util.*;

class Solution {
    public int solution(String[] s1, String[] s2) {
        int answer = 0;
        
        for(int i=0;i<s1.length;i++) {
			for(int j=0;j<s2.length;j++) {
				if(s1[i].equals(s2[j])) answer++;
			}
		}
        
        return answer;
    }
}
```


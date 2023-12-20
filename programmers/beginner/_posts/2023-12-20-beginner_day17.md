---
title: "문자열, 수학, 조건문, 배열, 사칙연산"
tag: beginner
---

### 숫자 찾기
![숫자 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/939e7d2f-3b2f-41c7-a8ab-356377639425)

```java
class Solution {
    public int solution(int num, int k) {
        int answer = -1;
		
		String n = String.valueOf(num);
		
		for(int i=0;i<n.length();i++) {
			char ch = n.charAt(i);
			if((ch-48)==k) {
				if(answer==-1) answer = i+1;
			}
		}
        
        return answer;
    }
}
```

---

### n의 배수 고르기
![n의 배수 고르기](https://github.com/yony-k/yony-k.github.io/assets/109204976/d0ded5a4-ab71-4b10-b16b-2cc61f37edc3)

```java
import java.util.*;

class Solution {
    public int[] solution(int n, int[] numlist) {
        int[] answer = {};
        
        answer = Arrays.stream(numlist).filter(i->i%n==0).toArray();
        
        return answer;
    }
}
```

---

### 자릿수 더하기
![자릿수 더하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/801f4cda-cfef-4362-a13f-45b673fb3c58)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        char[] tmp = String.valueOf(n).toCharArray();
		
		for(char ch : tmp) {
			answer += (ch-48);
		}
        
        return answer;
    }
}
```

---

### OX퀴즈
![OX퀴즈](https://github.com/yony-k/yony-k.github.io/assets/109204976/0b0e5295-a18f-4560-af1f-5710fa82ef0f)

```java
class Solution {
    public String[] solution(String[] quiz) {
        String[] answer = new String[quiz.length];
		
		int cnt =0;
		for(String s : quiz) {
			String[] sp = s.split(" ");
			int a = Integer.parseInt(sp[0]);
			int b = Integer.parseInt(sp[2]);
			int c = Integer.parseInt(sp[4]);
			if(sp[1].equals("+")) {
				answer[cnt++] = a+b==c ? "O" : "X";
			} else {
				answer[cnt++] = a-b==c ? "O" : "X";
			}
		}
        return answer;
    }
}
```


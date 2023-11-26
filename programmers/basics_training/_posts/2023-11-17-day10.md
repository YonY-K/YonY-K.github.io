---
title: "Day 10 문자열"
tag: basics_training
---

### 문자열의 앞의 n글자

![문자열의 앞의 n글자](https://github.com/yony-k/yony-k.github.io/assets/109204976/9a86a267-1c06-4096-a295-9eabf2e5b670)


```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";

        return answer=my_string.substring(0,n);
    }
}
```

---

### 접두사인지 확인하기

![접두사인지 확인하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/e8cdd57b-c543-4162-acc0-8392704db558)


```java
class Solution {
    public int solution(String my_string, String is_prefix) {
        int answer = 0;
        
        int len = is_prefix.length();

		if(len>my_string.length()) {
			answer = 0;
		} else {
			String str = my_string.substring(0,len);
			answer = is_prefix.equals(str)? 1 : 0;
		}
        
        return answer;
    }
}
```

---

### 문자열 뒤집기

![문자열 뒤집기](https://github.com/yony-k/yony-k.github.io/assets/109204976/db85b961-f1c7-4dc5-9ff3-5a8a56826dab)


```java
class Solution {
    public String solution(String my_string, int s, int e) {
        String answer = "";
		
		String reverse = my_string.substring(s,e+1);
		
		StringBuilder sb = new StringBuilder(reverse);
		reverse = sb.reverse().toString();
		
		answer = my_string.substring(0, s)+reverse+my_string.substring(e+1);
        
        return answer;
    }
}
```

---

### 세로 읽기

![세로 읽기](https://github.com/yony-k/yony-k.github.io/assets/109204976/3ab15369-220d-42f7-8de2-256a60a75180)


```java
class Solution {
    public String solution(String my_string, int m, int c) {
        String answer = "";
        
        int cnt = my_string.length()/m;
		
		for(int i=1,l=0;i<cnt+1;i++,l+=m) {
			String tmp =my_string.substring(l,m*i);
			answer += tmp.charAt(c-1);
		}
        
        return answer;
    }
}
```

---

### qr code

![qr code](https://github.com/yony-k/yony-k.github.io/assets/109204976/7a15325e-c206-4171-aa88-2a0297905f40)


```java
class Solution {
    public String solution(int q, int r, String code) {
        String answer = "";
        
        for(int i=0;i<code.length();i++) {
			if(i%q==r) answer += code.charAt(i);
		}
        
        return answer;
    }
}
```
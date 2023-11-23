---
title: "Day 16 문자열"
tag: basics_training
---

### 대문자로 바꾸기
![대문자로 바꾸기](https://github.com/yony-k/yony-k.github.io/assets/109204976/ee71ed41-ab85-49a3-b9d3-3407a869e53e)

```java
class Solution {
    public String solution(String myString) {
        String answer = myString.toUpperCase();
        return answer;
    }
}
```

---

### 소문자로 바꾸기
![소문자로 바꾸기](https://github.com/yony-k/yony-k.github.io/assets/109204976/f179eda7-5091-4a90-ab1e-b08ee179d73a)

```java
class Solution {
    public String solution(String myString) {
        String answer = myString.toLowerCase();
        return answer;
    }
}
```

---

### 배열에서 문자열 대소문자 변환하기
![배열에서 문자열 대소문자 변환하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/55bdf31c-391a-4689-95e0-91fcbef26b3a)

```java
class Solution {
    public String[] solution(String[] strArr) {
        
        for(int i=0;i<strArr.length;i++) {
			if(i%2==0) {
				strArr[i]=strArr[i].toLowerCase();
			} else {
				strArr[i]=strArr[i].toUpperCase();
			}
		}
        
        return strArr;
    }
}
```

---

### A 강조하기
![A 강조하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/17913f44-9d71-49ed-aa1a-97877b956cae)

```java
class Solution {
    public String solution(String myString) {
        String answer = "";
        
        for(int i=0;i<myString.length();i++) {
			char ch = myString.charAt(i);
			if(ch==97) answer += (char)65;
			else if(ch>65&& ch<=90) answer += (char)(ch+32);
			else answer += ch;
		}
        
        return answer;
    }
}
```

---

### 특정한 문자를 대문자로 바꾸기
![특정한 문자를 대문자로 바꾸기](https://github.com/yony-k/yony-k.github.io/assets/109204976/7b78a378-fb5b-42b1-b79d-9691b516481f)

```java
class Solution {
    public String solution(String my_string, String alp) {
        String answer = "";
        
        String tmp = alp.toUpperCase();
		
		answer= my_string.replaceAll(alp, tmp);
        
        return answer;
    }
}
```


---
title: "Day 17 문자열"
tag: basics_training
---

### 특정 문자열로 끝나는 가장 긴 부분 문자열 찾기

![특정 문자열로 끝나는 가장 긴 부분 문자열 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/ac76a59a-e955-4e83-8d1b-6689260c8fc6)

```java
class Solution {
    public String solution(String myString, String pat) {
        String answer = "";
        
        int find = myString.lastIndexOf(pat);
		
		answer = myString.substring(0, find+pat.length());
        
        return answer;
    }
}
```

---

### 문자열이 몇 번 등장하는지 세기

![문자열이 몇 번 등장하는지 세기](https://github.com/yony-k/yony-k.github.io/assets/109204976/1d20f84e-4cae-4747-81bb-aed2b794b995)

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        
		while(true) {
			int find = myString.indexOf(pat);
			if(find != -1) {
				myString =  myString.substring(find+1);
				answer++;
			} else {
				break;
			}
		}
        
        return answer;
    }
}
```

---

### ad 제거하기

![ad 제거하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/475ffb75-10b8-43ae-9cb3-ae270f1b4d0a)

```java
import java.util.*;

class Solution {
    public String[] solution(String[] strArr) {
        String[] answer = {};
        
        List<String> list = new ArrayList<String>();
		
		for(int i=0;i<strArr.length;i++) {
			if(strArr[i].contains("ad")) { 
				continue;
			} else {
				list.add(strArr[i]);
			}
		}
        
        return answer = list.toArray(new String[list.size()]);
    }
}
```

---

### 공백으로 구분하기 1

![공백으로 구분하기 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/12b7bb5b-d8d2-4c45-b51e-d8f4e46ffeee)

```java
class Solution {
    public String[] solution(String my_string) {
        String[] answer = {};
        return answer = my_string.split(" ");
    }
}
```

---

### 공백으로 구분하기 2

![공백으로 구분하기 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/02a01c4f-bb42-4679-87cd-c8c014ddf546)

```java
import java.util.*;

class Solution {
    public String[] solution(String my_string) {
        String[] answer = {};
        
        StringTokenizer st = new StringTokenizer(my_string," ");
		List<String> list = new ArrayList<String>();
		
		while(st.hasMoreTokens()) {
			list.add(st.nextToken());
		}
        
        return answer = list.toArray(new String[list.size()]);
    }
}
```
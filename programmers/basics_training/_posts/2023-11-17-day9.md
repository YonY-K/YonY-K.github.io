---
title: "Day 9 문자열"
tag: basics_training
---

### 배열 만들기 5

![배열 만들기 5](https://github.com/yony-k/yony-k.github.io/assets/109204976/a66d9952-95d1-4e8e-ae6a-939c199a41d7)


```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public int[] solution(String[] intStrs, int k, int s, int l) {
        int[] answer;
	
        List<Integer> list = new ArrayList<Integer>();
        
		for(int i=0,cnt=0;i<intStrs.length;i++) {
			int tmp = Integer.parseInt(intStrs[i].substring(s,s+l));
			if (tmp>k) {
				list.add(tmp);
			}
		}
        return answer = list.stream()
				.mapToInt(i->i)
				.toArray();
    }
}
```

---

### 부분 문자열 이어 붙여 문자열 만들기

![부분 문자열 이어 붙여 문자열 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/2f039e92-2a6a-4e7b-999e-f54868a776d1)


```java
class Solution {
    public String solution(String[] my_strings, int[][] parts) {
        String answer = "";
        
        for(int i=0;i<parts.length;i++) {
			int s = parts[i][0];
			int e = parts[i][1];
			
			answer += my_strings[i].subSequence(s, e+1);
		}
        
        return answer;
    }
}
```

---

### 문자열의 뒤의 n글자

![문자열 뒤의 n글자](https://github.com/yony-k/yony-k.github.io/assets/109204976/601fc938-3aa5-4574-b660-f8b9f4ee1588)


```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
  
        return answer=my_string.substring(my_string.length()-n);
    }
}
```

---

### 접미사 배열

![접미사 배열](https://github.com/yony-k/yony-k.github.io/assets/109204976/58486a0f-c0fb-4093-ae6d-8321759d9c7c)


```java
import java.util.*;

class Solution {
    public String[] solution(String my_string) {
        String[] answer;
        
        List<String> list = new ArrayList<String>();
		
		for(int i=0;i<my_string.length();i++) {
			list.add(my_string.substring(i));
		}
		
		Collections.sort(list);
        
        return answer=list.toArray(new String[list.size()]);
    }
}
```

---

### 접미사인지 확인하기

![접미사인지 확인하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/9999ba40-79cb-44e2-9488-cdefffb9e513)


```java
class Solution {
    public int solution(String my_string, String is_suffix) {
        int answer = 0;
        
        int len = my_string.length()-is_suffix.length();
		
		if(len<0) {
			answer = 0;
		} else {
			String str = my_string.substring(len);
			answer = is_suffix.equals(str)? 1 : 0;
		}
        
        return answer;
    }
}
```



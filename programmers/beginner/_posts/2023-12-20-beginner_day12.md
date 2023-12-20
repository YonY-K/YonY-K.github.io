---
title: "문자열, 정렬, 사칙연산, 수학"
tag: beginner
---

### 모음 제거
![모음 제거](https://github.com/yony-k/yony-k.github.io/assets/109204976/334d1b4d-f4b2-4e20-970e-448a656072e0)

```java
class Solution {
    public String solution(String my_string) {
        String answer = "";
        
        String[] gather = {"a", "e", "i", "o", "u"};
		
		for(String a : gather) {
			my_string = my_string.replace(a, "");
		}
        
        return answer=my_string;
    }
}
```

---

### 문자열 정렬하기 (1)
![문자열 정렬하기 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/61224799-c6aa-4ea9-be63-8228a4cb9791)

```java
import java.util.*;

class Solution {
    public int[] solution(String my_string) {
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=0;i<my_string.length();i++) {
			char ch = my_string.charAt(i);
			if(ch>=48&&ch<=57) list.add(Integer.valueOf(String.valueOf(ch)));
		}
		list.sort(Comparator.naturalOrder());
		int[] answer = list.stream().mapToInt(i->i.intValue()).toArray();
        return answer;
    }
}
```

---

### 숨어있는 숫자의 덧셈 (1)
![숨어있는 숫자의 덧셈 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/04bb91d7-9160-425b-ad36-cc3a32ff57b6)

```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        
        my_string = my_string.replaceAll("[A-Z|a-z]", "");
		
		for(int i=0;i<my_string.length();i++) {
			answer += Integer.parseInt(String.valueOf(my_string.charAt(i)));
		}
        
        return answer;
    }
}
```

---

### 소인수분해
![소인수분해](https://github.com/yony-k/yony-k.github.io/assets/109204976/dc77b36c-26c3-4d6f-896e-b9eac585ea4f)

```java
import java.util.*;

class Solution {
    public int[] solution(int n) {
        int[] answer = {};
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=2;i<=n;i++) {
			while(n%i==0) {
				if(!list.contains(i)) list.add(i);
				n/=i;
			}
		}
        
		answer = list.stream().mapToInt(i->i.intValue()).toArray();
        
        return answer;
    }
}
```


---
title: "Day 18 문자열"
tag: basics_training
---

### x 사이의 개수

![x 사이의 개수](https://github.com/yony-k/yony-k.github.io/assets/109204976/bb5562ab-79d5-48db-8933-c097d5fb7135)

```java
import java.util.*;

class Solution {
    public int[] solution(String myString) {
        int[] answer = {};
        
        String[] s = myString.split("x",-1);
		
		answer = Arrays.stream(s).map(i -> i.length()).mapToInt(i -> i.intValue()).toArray();
		
		return answer;
            
    }
}
```

---

### 문자열 잘라서 정렬하기

![문자열 잘라서 정렬하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/80239a02-ca25-4ba2-8b9c-5a82149e9be1)

```java
import java.util.*;

class Solution {
    public List solution(String myString) {

        StringTokenizer st = new StringTokenizer(myString,"x");
		List<String> answer = new ArrayList<>();
		
		while(st.hasMoreTokens()) {
			answer.add(st.nextToken());
		}
		
		answer.sort(null);
        
        return answer;
    }
}
```

---

### 간단한 식 계산하기

![간단한 식 계산하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/23de6709-9918-4308-83db-e5ae98b65d36)

```java
class Solution {
    public int solution(String binomial) {
        int answer = calculate(binomial);
        
        
        
        return answer;
    }
    
    static int calculate(String input) {
		
		String[] tmp = input.split(" ");
		
		int a = Integer.parseInt(tmp[0]);
		int b = Integer.parseInt(tmp[2]);
		int result = 0;
		
		switch(tmp[1]) {
		case "+":
			result = a + b;
			break;
		case "-":
			 result = a - b;
			 break;
		case "*":
			result = a * b;
			break;
		}
		
		return result;
	}
}
```

---

### 문자열 바꿔서 찾기

![문자열 바꿔서 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a1d62a60-d547-44a4-b2ab-037cfcb23023)

```java
class Solution {
    public int solution(String myString, String pat) {
        String tmp = "";
		
		for(int i=0;i<myString.length();i++) {
			tmp += myString.charAt(i)=='A'?"B" :"A";
		}
		
		int answer = tmp.contains(pat)?1:0;
        
        return answer;
    }
}
```

---

### rny_string

![rny_string](https://github.com/yony-k/yony-k.github.io/assets/109204976/1c0dcc4e-3918-438c-89ae-ec3fae64b222)

```java
class Solution {
    public String solution(String rny_string) {

		String answer = rny_string.replaceAll("m", "rn");

        return answer;
    }
}
```
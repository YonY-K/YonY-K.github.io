---
title: "문자열, 해시, 배열, 수학"
tag: beginner
---

### 영어가 싫어요
![영어가 싫어요](https://github.com/yony-k/yony-k.github.io/assets/109204976/1ca58a24-f23a-4433-9ed0-3622902e11ee)

```java
class Solution {
    public long solution(String numbers) {
        long answer = 0;
        String num = "";
		
		for(int i=0;i<numbers.length();) {
			if(numbers.charAt(i)=='z') {
				num += 0;
				i+=4;
			} else if(numbers.charAt(i)=='o'){
				num += 1;
				i+=3;
			} else if(numbers.charAt(i)=='t') {
				if(numbers.charAt(i+1)=='w') {
					num += 2;
					i+=3;
				} else {
					num += 3;
					i+=5;
				}
			} else if(numbers.charAt(i)=='f') {
				if(numbers.charAt(i+1)=='o') {
					num += 4;
					i+=4;
				} else {
					num += 5;
					i+=4;
				}
			} else if(numbers.charAt(i)=='s') {
				if(numbers.charAt(i+1)=='i') {
					num += 6;
					i+=3;
				} else {
					num += 7;
					i+=5;
				}
			} else if(numbers.charAt(i)=='e'){
				num += 8;
				i+=5;
			} else if(numbers.charAt(i)=='n'){
				num += 9;
				i+=4;
			} 
		}
		
		answer = Long.parseLong(num);
        return answer;
    }
}
```

---

### 인덱스 바꾸기
![인덱스 바꾸기](https://github.com/yony-k/yony-k.github.io/assets/109204976/da017da3-6bab-4f53-8711-9b788c4d4575)

```java
class Solution {
    public String solution(String my_string, int num1, int num2) {
        StringBuilder sb = new StringBuilder(my_string);
		char ch1 = my_string.charAt(num1);
		char ch2 = my_string.charAt(num2);
		sb.setCharAt(num1,ch2);
		sb.setCharAt(num2, ch1);
		
		String answer = sb.toString();
        return answer;
    }
}
```

---

### 한 번만 등장한 문자
![한 번만 등장한 문자](https://github.com/yony-k/yony-k.github.io/assets/109204976/9f1023b4-3ebe-4696-bcbd-b1ca1d3c0e64)

```java
import java.util.*;
import java.util.stream.*;

class Solution {
    public String solution(String s) {
        String answer = "";
        
        List<String> list = Arrays.asList(s.split(""));
		
		answer = list.stream()
				.sorted()
				.filter(i-> Collections.frequency(list, i) == 1)
				.collect(Collectors.joining());
        
        return answer;
    }
}
```

---

### 약수 구하기
![약수 구하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/504ca532-eac3-4b1e-b4eb-6a4b41a8b6a3)

```java
import java.util.*;
import java.util.stream.*;

class Solution {
    public int[] solution(int n) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=1;i<=Math.sqrt((double)n);i++) {
			if(n%i==0) {
				list.add(i);
				if(i!=Math.sqrt((double)n))list.add(n/i);
			}
		}
		
		answer = list.stream().distinct().sorted().mapToInt(i->i.intValue()).toArray();
        
        return answer;
    }
}
```


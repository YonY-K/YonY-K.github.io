---
title: "함수(메서드), 조건문 활용"
tag: basics_training
---

### 0 떼기
![0 떼기](https://github.com/yony-k/yony-k.github.io/assets/109204976/efc573de-62bc-4a9e-993a-f7a47b380f70)

```java
class Solution {
    public String solution(String n_str) {
        String answer = "";
        
        answer = String.valueOf(Integer.parseInt(n_str));
        return answer;
    }
}
```

---

### 두 수의 합
![두 수의 합](https://github.com/yony-k/yony-k.github.io/assets/109204976/8713b3ab-39b1-40ce-968a-3d32cf69ea43)

```java
import java.math.BigInteger;

class Solution {
    public String solution(String a, String b) {
        String answer = "";
        
        BigInteger c=new BigInteger(a);
		BigInteger d=new BigInteger(b);
		BigInteger sum = c.add(d);
		
		answer = sum.toString();
        
        return answer;
    }
}
```

---

### 문자열로 변환
![문자열로 변환](https://github.com/yony-k/yony-k.github.io/assets/109204976/aa7deff8-8034-4818-9328-5e244a4d05ba)

```java
class Solution {
    public String solution(int n) {
        String answer = String.valueOf(n);
        return answer;
    }
}
```

---

### 배열의 원소 삭제하기
![배열의 원소 삭제하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/7f3d9d0e-9010-4699-8654-252e31eba44b)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int[] delete_list) {
        int[] answer = {};
        
        for(int i=0;i<delete_list.length;i++) {
			for(int j=0;j<arr.length;j++) {
				if(delete_list[i]==arr[j]) {
					arr[j]=0;
				}
			}
		}
		
		List<Integer> list = new ArrayList<Integer>();
		for(int i=0;i<arr.length;i++) {
			if(arr[i]!=0) {
				list.add(arr[i]);
			}
		}
		
		answer = list.stream().mapToInt(i->i).toArray();
        
        return answer;
    }
}
```

---

### 부분 문자열인지 확인하기
![부분 문자열인지 확인하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a6934fa4-249f-4a95-a8d8-5b9a5ac42013)

```java
class Solution {
    public int solution(String my_string, String target) {
        int answer = 0;
        
        answer = my_string.contains(target) ? 1 : 0;
        
        return answer;
    }
}
```

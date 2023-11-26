---
title: "Day 15 리스트(배열), 문자열"
tag: basics_training
---

### 조건에 맞게 수열 변환화기 1

![조건에 맞게 수열 변환하기 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/c54b2ee6-2580-45e2-b04e-3a41d48c8649)


```java
class Solution {
    public int[] solution(int[] arr) {
        
        for(int i=0;i<arr.length;i++) {
			if(arr[i]>=50 && arr[i]%2==0) arr[i] /= 2;
			else if (arr[i]<50 && arr[i]%2!=0) arr[i] *= 2;
		}
        
        return arr;
    }
}
```

---

### 조건에 맞게 수열 변환하기 2

![조건에 맞게 수열 변환하기 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/36a77715-40d9-45fd-93b6-ad68e8dfd873)


```java
import java.util.*;

class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        
        int[] before;
		int[] after;
		
		while(true) {
			
			before = arr.clone();
			
			for(int i=0;i<arr.length;i++) {
				if(arr[i]>=50 && arr[i]%2==0) arr[i] /= 2;
				else if (arr[i]<50 && arr[i]%2!=0) arr[i] = arr[i]*2+1;
			}
			
			after = arr.clone();
			
			answer++;
			
			if(Arrays.equals(before, after)) break;
		}
        
        return answer-1;
    }
}
```

---

### 1로 만들기

![1로 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/7e71d7fc-7d9d-4a4f-8a55-47eb4ebb6b9c)


```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
		
		for(int i=0;i<num_list.length;i++) {
			for(int j=num_list[i];j>1;answer++) {
				if(j%2==0) j /= 2;
				else j = (j-1)/2;
			}
		}
        
        return answer;
    }
}
```

---

### 길이에 따른 연산

![길이에 따른 연산](https://github.com/yony-k/yony-k.github.io/assets/109204976/08d4a89d-1c8b-4c72-9d60-eb4c5f582ae5)


```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        
        if(num_list.length>=11) {
			for(int i : num_list) {
				answer += i;
			}
		} else {
			answer = 1;
			for(int i : num_list) {
				answer *= i;
			}
		}
        
        return answer;
    }
}
```

---

### 원하는 문자열 찾기

![원하는 문자열 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/b641cff8-4fcb-4aab-beca-8eb5ae460a56)


```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        
        myString = myString.toUpperCase();
		pat = pat.toUpperCase();
        
        if(myString.contains(pat)) answer = 1;
        
        return answer;
    }
}
```
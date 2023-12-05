---
title: "Day 11 리스트(배열)"
tag: basics_training
---

### 문자 개수 세기
![문자 개수 세기](https://github.com/yony-k/yony-k.github.io/assets/109204976/54c26926-6808-4195-96b6-85f43cbe05e7)

```java
class Solution {
    public int[] solution(String my_string) {
        int[] answer = new int[52];

		for(int i=0;i<my_string.length();i++) {
			char ch = my_string.charAt(i);
			if(ch>=65&&ch<=90) {
				answer[ch-65]++;
			} else {
				answer[ch-71]++;
			}
		}

        return answer;
    }
}
```

---

### 배열 만들기 1
![배열 만들기 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/5439782a-ed55-4e97-9ed8-a65c849736e1)

```java
class Solution {
    public int[] solution(int n, int k) {
        int[] answer = new int[n/k];
				
		for(int i=1,j=0;i<=n;i++) {
			if(i%k==0) answer[j++] = i;
		}
        return answer;
    }
}
```

---

### 글자 지우기
![글자 지우기](https://github.com/yony-k/yony-k.github.io/assets/109204976/6502ca12-ea3d-48b7-a1a6-72fe4f0a1f47)

```java
class Solution {
    public String solution(String my_string, int[] indices) {
        String answer = "";
        
        for(int i=0;i<indices.length;i++) {
			my_string = my_string.substring(0,indices[i])+"가"+
					my_string.substring(indices[i]+1);
		}
	
		for(int i=0;i<my_string.length();i++) {
			char ch = my_string.charAt(i);
			answer += ch>122?"":ch;
		}
        
        return answer;
    }
}
```

---

### 카운트 다운
![카운트 다운](https://github.com/yony-k/yony-k.github.io/assets/109204976/11d0f016-5472-4a86-aca7-c8f6ae6f3857)

```java
import java.util.*;

class Solution {
    public List solution(int start, int end_num) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=start;i>=end_num;i--) {
			answer.add(i);
		}
        return answer;
    }
}
```

---

### 가까운 1 찾기
![가까운 1 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/2d87930b-fac4-4520-8808-0291459e267e)

```java
class Solution {
    public int solution(int[] arr, int idx) {
        int answer = 0;
        
        answer=Integer.MAX_VALUE;
		
		for(int i=idx;i<arr.length;i++) {
			if(arr[i]==1&&i<answer) {
				answer = i;
			}
		}
		
		answer = answer==Integer.MAX_VALUE?-1:answer;
        
        return answer;
    }
}
```


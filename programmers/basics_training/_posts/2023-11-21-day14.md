---
title: "Day 14 리스트(배열)"
tag: basics_training
---

### 홀수 vs 짝수
![홀수 vs 짝수](https://github.com/yony-k/yony-k.github.io/assets/109204976/f3bd6acc-a2bf-4e44-99bc-21b5a2775294)

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        
        int sumEven=0;
		int sumOdd=0;
		
		for(int i=0;i<num_list.length;i++) {
			if(i%2==0) {
				sumEven+=num_list[i];
			} else {
				sumOdd+=num_list[i];
			}
		}
		
		if(sumEven>sumOdd) answer = sumEven;
		else if(sumEven<sumOdd) answer = sumOdd;
		else answer = sumEven;
        return answer;
    }
}
```

---

### 5명씩
![5명씩](https://github.com/yony-k/yony-k.github.io/assets/109204976/019fb324-1a20-4c31-a738-6776a0738a98)

```java
import java.util.*;

class Solution {
    public List solution(String[] names) {
        List<String> answer = new ArrayList<String>();
		
		for(int i=0;i<names.length;i+=5) {
			answer.add(names[i]);
		}
        return answer;
    }
}
```

---

### 할 일 목록
![할 일 목록](https://github.com/yony-k/yony-k.github.io/assets/109204976/8600e3f6-bb52-4d2e-955a-541820fafc2d)

```java
import java.util.*;

class Solution {
    public String[] solution(String[] todo_list, boolean[] finished) {
        
        String[] answer;
		
		int cnt=0;
		
		for(int i=0;i<finished.length;i++) {
			if(!finished[i]) cnt++;
		}
		
		answer = new String[cnt];
		
		for(int i=0,j=0;i<finished.length;i++) {
			if(!finished[i]) {
				answer[j++]=todo_list[i];
			}
		}
        
        return answer;
    }
}
```

---

### n보다 커질 때까지 더하기
![n보다 커질 때까지 더하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/83753d0b-9830-4a9e-8e6d-58cb85ad6496)

```java
class Solution {
    public int solution(int[] numbers, int n) {
        int answer = 0;
        for(int i=0;answer<=n;i++) {
			answer += numbers[i];
		}
        return answer;
    }
}
```

---

### 수열과 구간 쿼리 1
![수열과 구간 쿼리 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/31246f31-e942-441b-8ece-78f334856334)

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        
        for(int i=0;i<queries.length;i++) {
			int s = queries[i][0];
			int e = queries[i][1];
			
			for(int j=s;j<=e;j++) {
				arr[j]++;
			}
		}
        
        return arr;
    }
}
```


---
title: "사칙연산, 배열, 수학"
tag: beginner
---

### 나머지 구하기
![나머지 구하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/4ab77486-cd15-4788-93ba-7fe0d512940c)

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = -1;
        return answer=num1%num2;
    }
}
```

---

### 중앙값 구하기
![중앙값 구하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/8fac47b3-9606-47c4-85d0-6d61f325b253)

```java
import java.util.*;

class Solution {
    public int solution(int[] array) {
        int answer = 0;
        Arrays.sort(array);
		
		answer = array[(array.length/2)];
        return answer;
    }
}
```

---

### 최빈값 구하기
![최빈값 구하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/9f0f2beb-efa3-4f23-97f2-789436f530b1)

```java
import java.util.*;

class Solution {
    public int solution(int[] array) {
        int answer = 0;
        
        Arrays.sort(array);
		
		int big = array[array.length-1];
		
		int[] find = new int[big+1];
		
		for(int a : array) {
			find[a]++;
		}
		
		int max=Integer.MIN_VALUE;

		for(int i=0;i<find.length;i++) {
			if(max<find[i]) {
				max = find[i];
				answer = i;
			} else if(max == find[i]) answer = -1;  
		}
        
        return answer;
    }
}
```

---

### 짝수는 싫어요
![짝수는 싫어요](https://github.com/yony-k/yony-k.github.io/assets/109204976/faaae50f-60ed-4b8c-bb7f-ba45ee384a3c)

```java
import java.util.*;

class Solution {
    public int[] solution(int n) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=n;i>0;i--) {
			if(i%2==1) list.add(i);
		}
		
		answer = list.stream().sorted().mapToInt(i->i).toArray();
		
		System.out.println(Arrays.toString(answer));	
        
        return answer;
    }
}
```


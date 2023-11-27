---
title: "Day 20 함수(메서드)"
tag: basics_training
---

### 배열의 길이를 2의 거듭제곱으로 만들기
![배열의 길이를 2의 거듭제곱으로 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/08d980db-43df-4f8c-8408-228d2e5d1ff9)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr) {
        int len=arr.length;
		
		while(len%2==0) {
			len /= 2;
		}
		if(len==1) return arr;
		
		len=arr.length;
		int x=0;
		int y=0;
		while(x< len) {
			x = (int)Math.pow(2,y++);
			System.out.println(x);
		}
		System.out.println(x);
		
		int[] answer = new int[x];
		
		
		
		for(int i=0;i<arr.length;i++) {
			answer[i] = arr[i];
		}
        
        return answer;
    }
}
```

---

### 배열 비교하기
![배열 비교하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/642abf48-4ee9-4df4-8c5f-f05a4ec7493e)

```java
import java.util.*;

class Solution {
    public int solution(int[] arr1, int[] arr2) {
        int answer = 0;
        
        if(arr1.length>arr2.length) answer = 1;
		else if(arr1.length<arr2.length) answer = -1;
		else {
			int sum1 = Arrays.stream(arr1).sum();
			int sum2 = Arrays.stream(arr2).sum();
			if(sum1>sum2) answer = 1;
			else if(sum1<sum2) answer =-1;
		}
        
        return answer;
    }
}
```

---

### 문자열 묶기
![문자열 묶기](https://github.com/yony-k/yony-k.github.io/assets/109204976/365f7bbb-503a-4480-bf07-c1b51b92728f)

```java
import java.util.*;

class Solution {
    public int solution(String[] strArr) {
        
        int[] count = new int[31];
		
		for(int i=0;i<strArr.length;i++) {
			count[strArr[i].length()]++;
		}
		
		int answer = Arrays.stream(count).max().getAsInt();
        
        return answer;
    }
}
```

---

### 배열의 길이에 따라 다른 연산하기
![배열의 길이에 따라 다른 연산하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/41049807-94b8-440e-aa6e-6de8fa48b39e)

```java
class Solution {
    public int[] solution(int[] arr, int n) {
        
        
        if(arr.length%2!=0) {
			for(int i=0;i<arr.length;i+=2) {
				arr[i] += n;
			} 
		} else {
			for(int i=1;i<arr.length;i+=2) {
				arr[i] += n;
			}
		}
        
        return arr;
    }
}
```

---

### 뒤에서 5등까지
![뒤에서 5등까지](https://github.com/yony-k/yony-k.github.io/assets/109204976/917ac8a1-aed8-4420-a5be-6b2780dadfe3)

```java
import java.util.*;


class Solution {
    public int[] solution(int[] num_list) {
        
        Arrays.sort(num_list);
		
		int[] answer = Arrays.stream(num_list).limit(5).toArray();
        
        return answer;
    }
}
```
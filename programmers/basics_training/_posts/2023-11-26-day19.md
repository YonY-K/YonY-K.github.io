---
title: "Day 19 문자열, 리스트(배열)"
tag: basics_training
---

### 세 개의 구분자

![세 개의 구분자](https://github.com/yony-k/yony-k.github.io/assets/109204976/242d8099-0c63-4e50-8dda-dd351adccc31)

```java
import java.util.*;

class Solution {
    public String[] solution(String myStr) {

        StringTokenizer st = new StringTokenizer(myStr,"a|b|c");
		
		List<String> list = new ArrayList<String>();
		
		if(st.countTokens()==0) {
			list.add("EMPTY");
		} else {
			while(st.hasMoreTokens()) {
				list.add(st.nextToken());
			}
		}

		String[] answer = list.toArray(String[] :: new);
        
        return answer;
    }
}
```

---

### 배열의 원소만큼 추가하기

![배열의 원소만큼 추가하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/0260474a-3ceb-4f75-b155-a21cf7978b8c)

```java
import java.util.*;

class Solution {
    public List solution(int[] arr) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=0;i<arr.length;i++) {
			int tmp = arr[i];
			for(int j=0;j<tmp;j++) {
				answer.add(arr[i]);
			}
		}
        
        return answer;
    }
}
```

---

### 빈 배열에 추가, 삭제하기

![빈 배열에 추가, 삭제하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/392fc77d-9314-4afc-abd3-8b1e820726ba)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List solution(int[] arr, boolean[] flag) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=0;i<flag.length;i++) {
			if(flag[i]) {
				for(int j=0;j<arr[i]*2;j++) {
					answer.add(arr[i]);
				}
			} else {
				for(int j=0;j<arr[i];j++) {
					answer.remove(answer.size()-1);
				}	
			}
		}
        return answer;
    }
}
```

---

### 배열 만들기 6

![배열 만들기 6](https://github.com/yony-k/yony-k.github.io/assets/109204976/fe5e980f-4a28-4f50-ad09-8c2bb07526e0)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List solution(int[] arr) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=0;i<arr.length;i++) {
			if(answer.isEmpty()) {
				answer.add(arr[i]);
			} else if(answer.get(answer.size()-1)==arr[i]) {
				answer.remove(answer.size()-1);
			} else {
				answer.add(arr[i]);
			}
		}
		
		if(answer.isEmpty()) answer.add(-1);
        
        return answer;
    }
}
```

---

### 무작위로 K개의 수 뽑기

![무작위로 K개의 수 뽑기](https://github.com/yony-k/yony-k.github.io/assets/109204976/d59d22aa-c792-44e3-b3f7-35b691ecfa9e)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int k) {
        int[] answer = new int[k];
        
        arr=Arrays.stream(arr).distinct().toArray();
		 
		 if(arr.length>=k) {
			 for(int i=0;i<k;i++) {
				 answer[i]=arr[i];
			 } 
		 } else {
			 for(int i=0;i<k;i++) {
				 if(i<=arr.length-1) {
					 answer[i]=arr[i];
				 } else {
					 answer[i]=-1;
				 }
			 }
		 }
        
        return answer;
    }
}
```
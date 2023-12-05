---
title: "Day 12 리스트(배열)"
tag: basics_training
---

### 리스트 자르기
![리스트 자르기](https://github.com/yony-k/yony-k.github.io/assets/109204976/05061bd4-232d-4e21-9307-3f15c969b851)

```java
import java.util.*;

class Solution {
    public List solution(int n, int[] slicer, int[] num_list) {
        List<Integer> answer = new ArrayList<>();
		
		
		if(n==1) {
			for(int i=0;i<=slicer[1];i++) {
				answer.add(num_list[i]);
			}
		}else if(n==2) {
			for(int i=slicer[0];i<num_list.length;i++) {
				answer.add(num_list[i]);
			}
		}else if(n==3) {
			for(int i=slicer[0];i<=slicer[1];i++) {
				answer.add(num_list[i]);
			}
		}else if(n==4)  {
			for(int i=slicer[0];i<=slicer[1];i+=2) {
				answer.add(num_list[i]);
			}
		}
        
        return answer;
    }
}
```

---

### 첫 번째로 나오는 음수
![첫 번째로 나오는 음수](https://github.com/yony-k/yony-k.github.io/assets/109204976/15cb06a1-4af1-4118-9aba-1a48bff9de5b)

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        
        boolean find = false;
		
		for(int i=0;i<num_list.length;i++) {
			
			if(num_list[i]<0) {
				answer = i;
				find = true;
				break;
			}
		}
		
		answer = find ? answer : -1;
        
        return answer;
    }
}
```

---

### 배열 만들기 3
![배열 만들기 3](https://github.com/yony-k/yony-k.github.io/assets/109204976/6da8426b-d9f8-43f5-a8f4-20e735feed09)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int[][] intervals) {
        int[] answer;
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=0;i<intervals.length;i++) {
			int s = intervals[i][0];
			int e = intervals[i][1];
			
			for(int j=s;j<=e;j++) {
				list.add(arr[j]);
			}
		}

        return answer=list.stream().mapToInt(Integer :: intValue).toArray();
    }
}
```

---

### 2의 영역
![2의 영역](https://github.com/yony-k/yony-k.github.io/assets/109204976/5ac6a66f-fc16-4299-8918-b70528b5e7d2)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=0;i<arr.length;i++) {
			if(arr[i]==2) {
				list.add(i);
			}
		}
		
		if(list.isEmpty()) {
			answer= new int[] {-1};
		} else {
			int start = list.get(0);
			int end = list.get(list.size()-1);
			
			
			if(list.size()==1) {
				answer = new int[] {arr[start]};
			} else {
				answer = new int[end-start+1];
				for(int i=start,j=0;i<=end;i++) {
					answer[j++] = arr[i];
				}
			}	
		}
        
        return answer;
    }
}
```

---

### 배열 조각하기
![배열 조각하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/31b97e7e-e7cf-4bd9-adf2-c49616641103)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int[] query) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(int i=0;i<arr.length;i++) {
			list.add(arr[i]);
		}
		
		for(int i=0;i<query.length;i++) {
			int s = query[i];
			
			if(i%2==0) {
				int l = list.size();
				for(int j=s+1;j<l;j++) {
					list.remove(s+1);
				}
			} else {
				for(int j=0;j<s;j++) {
					list.remove(0);
				}
			}
		}
        
        return answer=list.stream().mapToInt(Integer :: intValue).toArray();
    }
}
```
---
title: "Day 7 반복문"
tag: basics_training
---

### 수열과 구간 쿼리 4

![수열과 구간 쿼리 4](https://github.com/yony-k/yony-k.github.io/assets/109204976/cacc8b62-05a7-4aa1-a3fb-d6a22fa116b7)


```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        
        for(int i=0;i<queries.length;i++) {
            int s = queries[i][0];
            int e = queries[i][1];
            int k = queries[i][2];
            
            for(int j=s;j<=e;j++) {
                if(j%k==0) arr[j]+=1;
            }
        }
        return arr;
    }
}
```

---


### 배열 만들기 2

![배열 만들기 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/3a9a71bc-797d-4660-beeb-a5fc781c4ee7)


```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List solution(int l, int r) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=l;i<=r;i++) {
			boolean pass = true;
			String s = String.valueOf(i);
			for(int j=0;j<s.length();j++) {
				char ch = s.charAt(j);
				if(ch!='0') {
					if(ch!='5') {
						pass = false;
						break;
					}
				}
			}
			
			if(pass) {
				answer.add(i);
			}
			
		}
		
		if(answer.size()==0) {
			answer.add(-1); 
		}
        return answer;
        
    }
}
```

---


### 카운트 업

![카운트 업](https://github.com/yony-k/yony-k.github.io/assets/109204976/746f7ca7-a9ba-4bad-8a6d-1602a1d76a24)


```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List solution(int start_num, int end_num) {
        List<Integer> answer = new ArrayList<>();
        
        for(int i=start_num;i<=end_num;i++) {
            answer.add(i);
        }
        
        
        return answer;
    }
}
```

---


### 콜라츠 수열 만들기

![콜라츠 수열 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/93320e8f-f48e-406d-832c-d256780cb979)


```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List solution(int n) {
        List<Integer> answer = new ArrayList<>();
		answer.add(n);
		
		
		for(int i=n;i>1; ) {
			if(i%2==0) {
                i=i/2;
                answer.add(i); 
            }
			else {
                i=3*i+1;
                answer.add(i);
            }
		}
        
        return answer;
    }
}
```

---


### 배열 만들기 4

![배열 만들기 4](https://github.com/yony-k/yony-k.github.io/assets/109204976/37a805d0-a990-48e0-a715-a0ac7ab7de7d)


```java
import java.util.ArrayList;
import java.util.List;


class Solution {
    public List solution(int[] arr) {
        List<Integer> list = new ArrayList<>();
        
        for(int i=0;i<arr.length;) {
            if(list.size()==0) {
            	list.add(arr[i]);
            	i++;
            } else {
            	if(list.get(list.size()-1)<arr[i]) {
            		list.add(arr[i]);
            		i++;
            	} else {
            		list.remove(list.size()-1);
            	}
            }
        }
        
        
        return list;
    }
}
```

---
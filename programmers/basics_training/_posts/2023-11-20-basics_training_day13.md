---
title: "Day 13 리스트(배열)"
tag: basics_training
---

### n 번째 원소부터
![n 번째 원소부터](https://github.com/yony-k/yony-k.github.io/assets/109204976/f9caafcd-6072-40c6-9280-ec3d11136f9e)

```java
import java.util.*;

class Solution {
    public List solution(int[] num_list, int n) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=n-1;i<num_list.length;i++) {
			answer.add(num_list[i]);
		}
        return answer;
    }
}
```

---

### 순서 바꾸기
![순서 바꾸기](https://github.com/yony-k/yony-k.github.io/assets/109204976/06dce28c-f96c-4ac3-80eb-2ce5d43eacec)

```java
import java.util.*;

class Solution {
    public List solution(int[] num_list, int n) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=n;i<num_list.length;i++) {
			answer.add(num_list[i]);
		}
		for(int i=0;i<n;i++) {
			answer.add(num_list[i]);
		}
        return answer;
    }
}
```

---

### 왼쪽 오른쪽
![왼쪽 오른쪽](https://github.com/yony-k/yony-k.github.io/assets/109204976/c8e4827a-167c-488f-9a97-e7de12a20911)

```java
import java.util.*;

class Solution {
    public List solution(String[] str_list) {
        List<String> answer = new ArrayList<String>();
        
        for(int i=0;i<str_list.length;i++) {
			if(str_list[i].equals("l")) {
				for(int j=0;j<i;j++) {
					answer.add(str_list[j]);
				}
				break;
			} else if(str_list[i].equals("r")) {
				for(int j=i+1;j<str_list.length;j++) {
					answer.add(str_list[j]);
				}
				break;
			}
		}
        
        return answer;
    }
}
```

---

### n 번째 원소까지
![n 번째 원소까지](https://github.com/yony-k/yony-k.github.io/assets/109204976/c60455e8-374c-4ffc-bbd2-eb3b3be03f66)

```java
import java.util.*;

class Solution {
    public List solution(int[] num_list, int n) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=0;i<n;i++) {
			answer.add(num_list[i]);
		}
        return answer;
    }
}
```

---

### n개 간격의 원소들
![n개 간격의 원소들](https://github.com/yony-k/yony-k.github.io/assets/109204976/5070231f-856d-4528-acd4-4a259e9b7169)

```java
import java.util.*;

class Solution {
    public List solution(int[] num_list, int n) {
        List<Integer> answer = new ArrayList<Integer>();
		
		for(int i=0;i<num_list.length;i+=n) {
			answer.add(num_list[i]);
		}
        return answer;
    }
}
```


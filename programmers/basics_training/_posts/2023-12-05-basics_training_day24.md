---
title: "조건문 활용, 반복문 활용, 이차원 리스트(배열)"
tag: basics_training
---

### 커피 심부름
![커피 심부름](https://github.com/yony-k/yony-k.github.io/assets/109204976/87def2ac-9a9e-4d01-be23-8f257f03b616)

```java
class Solution {
    public int solution(String[] order) {
        int answer = 0;
        
        for(int i=0;i<order.length;i++) {
			if(order[i].contains("americanoice")) {
				answer += 4500;
			} else if(order[i].contains("cafelatte")) {
				answer += 5000;
			} else {
				answer += 4500;
			}
		}
        
        return answer;
    }
}
```

---

### 그림 확대
![그림 확대](https://github.com/yony-k/yony-k.github.io/assets/109204976/b98ad6ff-ee4e-4ffa-a648-4f1e86f4e8a8)

![그림 확대 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/ebda131b-f408-4f04-9a43-904ffd097858)

```java
import java.util.*;

class Solution {
    public List solution(String[] picture, int k) {
        List<String> answer = new ArrayList<String>();
        
        for(int i=0;i<picture.length;i++) {
			String original = picture[i];
			String tmp="";
			for(int j=0;j<original.length();j++) {
				for(int l=0;l<k;l++) {
					tmp += original.charAt(j);
				}
			}
			for(int j=0;j<k;j++) {
				answer.add(tmp);
			}
		}
        
        return answer;
    }
}
```

---

### 조건에 맞게 수열 변환하기 3
![조건에 맞게 수열 변환하기 3](https://github.com/yony-k/yony-k.github.io/assets/109204976/8d35343e-7dd3-467b-884c-2f5bf2c913c7)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int k) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		if(k%2!=0) {
			for(int i=0;i<arr.length;i++) {
				list.add(arr[i]*k);
			}
		} else {
			for(int i=0;i<arr.length;i++) {
				list.add(arr[i]+k);
			}
		}
		
		answer = list.stream().mapToInt(i->i).toArray();
        
        return answer;
    }
}
```

---

### l로 만들기
![l로 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/e61bf069-410e-44f6-ac94-090835b77859)

```java
class Solution {
    public String solution(String myString) {
        String answer = "";
        
        for(int i=0;i<myString.length();i++) {
			char ch = myString.charAt(i);
			if(ch<=108) answer += 'l';
			else answer += ch;
		}
        
        return answer;
    }
}
```

---

### 특별한 이차원 배열 1
![특별한 이차원 배열 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/5a4cf0fd-1538-4ec1-8e36-d3912a5749bb)

```java
class Solution {
    public int[][] solution(int n) {
        int[][] answer = new int[n][n];
		
		for(int i=0;i<answer.length;i++) {
			for(int j=0;j<answer[i].length;j++) {
				answer[i][j]=(i==j) ? 1 : 0;
			}
		}
        return answer;
    }
}
```

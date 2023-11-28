---
title: "Day 21 함수(메서드)"
tag: basics_training
---

### 뒤에서 5등 위로
![뒤에서 5등 위로](https://github.com/yony-k/yony-k.github.io/assets/109204976/a9e12a53-54f1-45e8-a04b-6fa9e2b7b886)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] num_list) {      
        
        Arrays.sort(num_list);
		int[] answer = Arrays.stream(num_list).skip(5).toArray();
        
        return answer;
    }
}
```

---

### 전국 대회 선발 고사
![전국 대회 선발 고사](https://github.com/yony-k/yony-k.github.io/assets/109204976/6a105486-ec3f-4414-ac54-9fd43d2041ca)

```java
import java.util.*;

class Solution {
    public int solution(int[] rank, boolean[] attendance) {
        int answer = 0;
        
        int[] score = rank.clone();
		Arrays.sort(score);
		
		int[] go = new int[3];
		
		for(int i=0,cnt=0;cnt<3;i++) {
			for(int j=0;j<rank.length;j++) {
				if(score[i]==rank[j]) {
					if(attendance[j]) {
						go[cnt++] = j;
						break;
					}
				}
			}
		}
        
        return answer = (10000*go[0]) + (100*go[1]) + (go[2]);
    }
}
```

---

### 정수 부분
![정수 부분](https://github.com/yony-k/yony-k.github.io/assets/109204976/3df39f26-5d99-450d-b437-9b21e2f09773)

```java
class Solution {
    public int solution(double flo) {
        int answer = (int)flo;
        return answer;
    }
}
```

---

### 문자열 정수의 합
![문자열 정수의 합](https://github.com/yony-k/yony-k.github.io/assets/109204976/bf64dcdc-d8d1-4aa9-b2f8-d0834c1968e2)

```java
class Solution {
    public int solution(String num_str) {
        
        String[] num = num_str.split("");
		
		int answer = 0;
		
		for(String s : num) {
			answer += Integer.parseInt(s);
		}
        
        return answer;
    }
}
```

---

### 문자열을 정수로 변환하기
![문자열을 정수로 변환하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/6c735f83-82e9-43ee-a7ae-4d0d3c219893)

```java
class Solution {
    public int solution(String n_str) {
        int answer = Integer.parseInt(n_str);
        return answer;
    }
}
```
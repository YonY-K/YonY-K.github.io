---
title: "조건문 활용"
tag: basics_training
---

### 부분 문자열
![부분 문자열](https://github.com/yony-k/yony-k.github.io/assets/109204976/8edb3dfc-c9e1-40b2-ad47-548f672ef037)

```java
class Solution {
    public int solution(String str1, String str2) {
        int answer = 0;
        
        answer = str2.contains(str1) ? 1 : 0;
        
        return answer;
    }
}
```

---

### 꼬리 문자열
![꼬리 문자열](https://github.com/yony-k/yony-k.github.io/assets/109204976/f18ea83d-80a3-4ec7-8f58-90c81f4b9bf4)

```java
class Solution {
    public String solution(String[] str_list, String ex) {
        String answer = "";
        
        for(int i=0;i<str_list.length;i++) {
			if(!str_list[i].contains(ex)) {
				answer += str_list[i];
			}
		}
        
        return answer;
    }
}
```

---

### 정수 찾기
![정수 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/824fe516-0b29-403d-b827-05ebbe420257)

```java
class Solution {
    public int solution(int[] num_list, int n) {
        int answer = 0;
        
        for(int i=0;i<num_list.length;i++) {
			if(num_list[i]==n) answer = 1;
		}
        
        return answer;
    }
}
```

---

### 주사위 게임 1
![주사위 게임 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/e6f24463-d7be-4045-bba8-23928c14c919)

```java
class Solution {
    public int solution(int a, int b) {
        int answer = 0;
        
        int c = a%2==0 ? 1 : 0;
		int d = b%2==0 ? 1 : 0;
		
		if(c==1&&d==1) {
			answer = Math.abs(a-b);
		} else if(c==0&&d==0) {
			answer = (a*a)+(b*b);
		} else {
			answer = 2*(a+b);
		}	
        
        return answer;
    }
}
```

---

### 날짜 비교하기
![날짜 비교하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/ff313166-2091-4bd2-a5bc-09bd696d408c)

```java
class Solution {
    public int solution(int[] date1, int[] date2) {
        int answer = 0;
        
        int[] find = new int[3]; 
		
		for(int i=0;i<date1.length;i++) {
			if(date1[i]<date2[i]) find[i]=1;
			else if(date1[i]>date2[i]) find[i]=-1;
			else find[i]=0;
		}
		
		if(find[0]==1) {
			answer = 1;
		} else if(find[0]==-1) {
			answer = 0;
		} else {
			if(find[1]==1) {
				answer = 1;
			} else if(find[1]==-1) {
				answer = 0;
			} else {
				if(find[2]==1) {
					answer = 1;
				} else if(find[2]==-1) {
					answer = 0;
				} else {
					answer = 0;
				}
			}
		}
        
        return answer;
    }
}
```

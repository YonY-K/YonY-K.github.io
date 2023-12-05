---
title: "수학, 배열"
tag: beginner
---

### 옷가게 할인 받기
![옷가게 할인 받기](https://github.com/yony-k/yony-k.github.io/assets/109204976/dd19307c-c66f-4efa-ad2d-982ec7e06742)

```java
class Solution {
    public int solution(int price) {
        int answer = 0;
        
        if(price>=500000) {
			answer = (int)(price-(price*0.2));
		} else if(price>=300000) {
			answer = (int)(price-(price*0.1));
		} else if(price>=100000) {
			answer = (int)(price-(price*0.05));
		} else answer = price;
        
        return answer;
    }
}
```

---

### 아이스 아메리카노
![아이스 아메리카노](https://github.com/yony-k/yony-k.github.io/assets/109204976/c38ceca1-4d46-4585-b8c2-c20d395e955a)

```java
class Solution {
    public int[] solution(int money) {
        int[] answer = new int[2];
		
		answer[0] = money/5500;
		answer[1] = money%5500;
        return answer;
    }
}
```

---

### 나이 출력
![나이 출력](https://github.com/yony-k/yony-k.github.io/assets/109204976/b597acc0-cbfa-434f-9330-25d844e8f63f)

```java
class Solution {
    public int solution(int age) {
        int answer = 2022-age+1;
        return answer;
    }
}
```

---

### 배열 뒤집기
![배열 뒤집기](https://github.com/yony-k/yony-k.github.io/assets/109204976/87aea274-c7fb-4a77-bbf5-b1f91f79c52d)

```java
class Solution {
    public int[] solution(int[] num_list) {
        int[] answer = new int[num_list.length];
		
		
		for(int i=num_list.length-1,j=0;i>=0;i--,j++) {
			answer[j] = num_list[i];
		}
        return answer;
    }
}
```
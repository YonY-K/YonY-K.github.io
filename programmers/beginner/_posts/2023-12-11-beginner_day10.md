---
title: "조건문, 배열, 수학, 시뮬레이션"
tag: beginner
---

### 점의 위치 구하기
![점의 위치 구하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/00d72964-83bc-42f1-bb89-8600db31fa00)

```java
class Solution {
    public int solution(int[] dot) {
        int answer = 0;
        
        if(dot[0]>0&&dot[1]>0) answer = 1;
        else if(dot[0]<0&&dot[1]>0) answer = 2;
        else if(dot[0]<0&&dot[1]<0) answer = 3;
        else if(dot[0]>0&&dot[1]<0) answer = 4;
        
        return answer;
    }
}
```

---

### 2차원으로 만들기
![2차원으로 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/d73df6c0-a4f4-41f9-801f-42c5a9827478)

```java
class Solution {
    public int[][] solution(int[] num_list, int n) {
        int[][] answer = new int[num_list.length/n][n];
		int cnt=0;
		
		for(int i=0;i<answer.length;i++) {
			for(int j=0;j<n;j++) {
				if(cnt==num_list.length-1) {
					answer[i][j]=num_list[cnt];
				} else {
					answer[i][j]=num_list[cnt++];
				}			
			}
		}
        
        
        return answer;
    }
}
```

- 2차원 배열의 크기는 [매개변수 배열의 길이/n][n]

---

### 공 던지기
![공 던지기](https://github.com/yony-k/yony-k.github.io/assets/109204976/8e410d5c-0080-4d06-a9f5-8e91bfaed5a0)

```java
class Solution {
    public int solution(int[] numbers, int k) {
        int answer = 0;

	    int n=(k-1)*2%numbers.length;
		
		answer = numbers[n];
        
        return answer;
    }
}
```

- 항렬...어쩌구가 연관되어있다는데 좀 더 공부 필요함
- 완벽히 이해하지 못했음

---

### 배열 회전시키기
![배열 회전시키기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a83689c6-4815-42bf-8d7d-8ec682014a71)

```java
class Solution {
    public int[] solution(int[] numbers, String direction) {
        int[] answer = new int[numbers.length];
		
		
		if(direction.equals("right")) {
			
			for(int i=0,j=numbers.length-1;i<answer.length;i++,j++) {
				if(j==numbers.length) j=0;
				answer[i]=numbers[j];
			}
			
		} else {
			for(int i=0,j=1;i<answer.length;i++,j++) {
				if(j==numbers.length) j=0;
				answer[i]=numbers[j];
			}
		}
        return answer;
    }
}
```

- 매개변수 문자열이 right 일때는 매개변수 배열의 위치값을 numbers.length-1 부터 시작해서 numbers.length이 되는 순간 0으로 바꿔주기
- 매개변수 문자열이 left 일때는 매개변수 배열의 위치값을 1부터 시작해서 numbers.length이 되는 순간 0으로 바꿔주기
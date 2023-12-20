---
title: "수학, 반복문"
tag: beginner
---

### 주사위의 개수
![주사위의 개수](https://github.com/yony-k/yony-k.github.io/assets/109204976/45223f32-fec9-4558-963c-9190fbb50748)

```java
class Solution {
    public int solution(int[] box, int n) {
        int answer = 0;
        
        answer = (box[0]/n)*(box[1]/n)*(box[2]/n);
        
        return answer;
    }
}
```

---

### 합성수 찾기
![합성수 찾기](https://github.com/yony-k/yony-k.github.io/assets/109204976/258b266a-b953-408f-97aa-fbc5c01c2168)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        int cnt = 0;
		for(int i=1;i<=n;i++) {
			cnt=0;
			for(int j=1;j<=i;j++) {
				if(i%j==0) cnt++;
				if(cnt==3) {
					answer++;
					break;
				}
			}
		}
        
        return answer;
    }
}
```

---

### 최댓값 만들기 (1)
![최댓값 만들기 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/6bee4cd1-2d34-4be5-8213-292751d009e7)

```java
class Solution {
    public int solution(int[] numbers) {
        int answer = Integer.MIN_VALUE;
		
		for(int i=0;i<numbers.length-1;i++) {
			int n = numbers[i];
			for(int j=i+1;j<numbers.length;j++) {
				if(answer<numbers[i]*numbers[j]) answer = numbers[i]*numbers[j];
			}
		}
        return answer;
    }
}
```

---

### 팩토리얼
![팩토리얼](https://github.com/yony-k/yony-k.github.io/assets/109204976/bba9d48b-eb51-4dbe-ac55-9cbb2e12409e)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        int num = 1;
		
		for(int i=1;i<=n;i++) {
			if((num*=i)>n) {
				answer= i-1;
				break;
			}
			if(i==n) answer = i;
		}
        
        return answer;
    }
}
```


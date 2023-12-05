---
title: "Day 6 조건문, 반복문"
tag: basics_training
---

### 마지막 두 원소
![마지막 두 원소](https://github.com/yony-k/yony-k.github.io/assets/109204976/fa91ef90-cb17-4f7c-bd33-5be7f6a2e3e0)

```java
class Solution {
    public int[] solution(int[] num_list) {
        int length = num_list.length;
		int[] answer = new int[length+1];
        
        int last = num_list[length-1];
        int fast = num_list[length-2];

        if(last>fast) {
            System.arraycopy(num_list, 0, answer, 0, length);
            answer[length]=answer[length-1]-answer[length-2];
        } else {
            System.arraycopy(num_list, 0, answer, 0, length);
            answer[length]=answer[length-1]*2;
        }

        /*
        System.arraycopy(num_list, 0, answer, 0, length);

        answer[length] = last>fast?last-fast:last*2;
        */
        return answer;
    }
}
```

- last가 fast 보다 큰지 작은지 검사하는 과정을 삼항 연산자로 보다 짧게 만들 수 있었다.

---

### 수 조작하기 1
![수 조작하기 1](https://github.com/yony-k/yony-k.github.io/assets/109204976/1605fcde-a4ae-4374-ad37-d1f13405381c)

```java
class Solution {
public int solution(int n, String control) {
    int answer = n;
    
    for(int i=0;i<control.length();i++) {
        char ch = control.charAt(i);
        if(ch=='w') answer++; 
        else if(ch=='s')  answer--;
        else if(ch=='d')  answer += 10; 
        else if(ch=='a')  answer -= 10;  
    }
    
    return answer;
}
}
```

---

### 수 조작하기 2
![수 조작하기 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/4251e073-190d-498e-8a9d-d482fe38032d)

```java
class Solution {
    public String solution(int[] numLog) {
        String answer = "";
        
        for(int i=1;i<numLog.length;i++) {
            int n = numLog[i]-numLog[i-1];
            if(n==1) answer += "w";
            else if(n==-1) answer += "s";
            else if(n==10) answer += "d";
            else if(n==-10) answer += "a";
		}
        
        return answer;
    }
}
```

---

### 수열과 구간 쿼리 3
![수열과 구간 쿼리 3](https://github.com/yony-k/yony-k.github.io/assets/109204976/f8859f95-55b9-4d0a-82cf-86bd5c93cecf)

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] answer = arr;
        
        for(int i=0;i<queries.length;i++) {
            int a = queries[i][0];
            int b = queries[i][1];

            int tmp = answer[a];
            answer[a] = answer[b];
            answer[b] = tmp;
        }
        
        return answer;
    }
}
```

---

### 수열과 구간 쿼리 2
![수열과 구간 쿼리 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/6fc3e19b-96cd-49c7-a261-0d4bd7415c79)

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] answer = new int[queries.length];		        
        for(int i=0;i<queries.length;i++) {
            int s = queries[i][0];
            int e = queries[i][1];
            int k = queries[i][2];

            int min = Integer.MAX_VALUE;
            for(int j=s;j<=e;j++) {
                if(arr[j]>k) {
                    min = Math.min(min, arr[j]);
                }
            }

            answer[i] = min==Integer.MAX_VALUE?-1 : min;

        }
        return answer;
    }
}
```
- answer 배열에 크기를 지정해줄 때 임의의 숫자로 지정을 해줬더니 런타임 오류가 계속 발생했다.
- 문제 접근 방식은 틀리지 않았다.
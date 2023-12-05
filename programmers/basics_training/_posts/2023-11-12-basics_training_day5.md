---
title: "Day 5 조건문"
tag: basics_training
---

### 코드 처리하기
![코드 처리하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/2e0dca6c-f350-494b-a9bc-de3f33937f8e)

```java
class Solution {
    public String solution(String code) {
        String answer = "";

        int mod = 0;
        String ret = "";
        
        for(int idx=0;idx<code.length();idx++){
            char ch = code.charAt(idx);
            if(mod==0) {
                if(ch=='1') {
                    mod = 1;
                } else {
                    ret += (idx%2==0)?ch:"";
                }
            } else {
                if(ch=='1') {
                    mod = 0;
                } else {
                    ret += idx%2!=0?ch:"";
                }
            }
        }
        
        return answer = ret.equals("")?"EMPTY":ret;
    }
}
```

- 문제 이해하는게 어려웠음
    - code[idx](문자하나) 가 1일 때만 mod를 바꿈
    - code[idx]가 1이 아닐 때 모드가 무슨 값인지 확인하고 모드가 0일때는 code[idx]가 짝수이면 저장 , 모드가 1일 때는 code[idx]가 홀수일 때 저장

<br>

```java
//다른 사람의 풀이
class Solution {
    public String solution(String code) {
        StringBuilder answer = new StringBuilder();
        int mode = 0;
        for (int i = 0; i < code.length(); i++) {
            char current = code.charAt(i);
            if (current == '1') {
                mode = mode == 0 ? 1 : 0;
                continue;
            }

            if (i % 2 == mode) {
                answer.append(current);
            }
        }
        return answer.length() == 0 ? "EMPTY" : answer.toString();
    }
}
```

---

### 등차수열의 특정한 항만 더하기
![등차수열의 특정한 항만 더하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/3dee72b5-80c8-4d1c-8628-53cafcab01c4)

```java
class Solution {
    public int solution(int a, int d, boolean[] included) {
        int answer = 0;
        
        for(int i=0;i<included.length;i++) {
	        	if(included[i]) answer += (a+(i*d));
	        }
        
        return answer;
    }
}
```

---

### 주사위 게임 2
![주사위 게임 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/071a9af2-6276-4bbb-941b-4daa0f2fc6e0)

```java
class Solution {
    public int solution(int a, int b, int c) {
        int answer = 0;
        
        if(a==b) {
	        	if(a==c) {
	        		answer = (a+b+c) *
		        			((a*a)+(b*b)+(c*c)) *
		        			((a*a*a)+(b*b*b)+(c*c*c));
	        	} else {
	        		answer = (a+b+c) *
		        			((a*a)+(b*b)+(c*c));
	        	}
	        	
	        } else {
	        	if(a==c) {
	        		answer = (a+b+c) *
		        			((a*a)+(b*b)+(c*c));
	        	} else if(b==c){
	        		answer = (a+b+c) *
		        			((a*a)+(b*b)+(c*c));
	        	} else {
	        		answer = a+b+c;
	        	}
	        
	        }
        
        return answer;
    }
}
```
- 경우의 수를 생각하는 게 어려웠다.
- a==b && a=c 인 경우
- a==b || a==c || b==c 인 경우
- a!=b && a!=c && b!=c 인 경우

---

### 원소들의 곱과 합
![원소들의 곱과 합](https://github.com/yony-k/yony-k.github.io/assets/109204976/3ba1acf2-b83d-4a07-b2b3-9a80b7eae516)

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        
        int sum = 0;
        int multi = 1;

        for(int num : num_list) {
            multi *= num;
            sum += num;
        }
        
        return answer = multi<sum*sum?1:0;
    }
}
```

---

### 이어 붙인 수
![이어 붙인 수](https://github.com/yony-k/yony-k.github.io/assets/109204976/b30ae7ac-52f8-43e6-a3a9-3cebf2bb988e)

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        String sumEven="";
        String sumOdd="";
        
        for(int num : num_list) {
            if(num%2==0) sumEven += String.valueOf(num);
            else sumOdd += String.valueOf(num);
        }
        
        return answer = Integer.parseInt(sumEven)+Integer.parseInt(sumOdd);
    }
}
```


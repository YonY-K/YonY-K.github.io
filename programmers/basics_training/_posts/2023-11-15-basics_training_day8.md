---
title: "Day 8 조건문, 문자열"
tag: basics_training
---

### 간단한 논리 연산
![간단한 논리 연산](https://github.com/yony-k/yony-k.github.io/assets/109204976/b43c3158-56e4-4c13-b746-c90ee24dcb92)

```java
class Solution {
    public boolean solution(boolean x1, boolean x2, boolean x3, boolean x4) {
        boolean answer = false;
        
        boolean x =false;
        boolean y =false;
   
        x = (x1||x2) ? true : false;
        y = (x3||x4) ? true : false;
        
        return answer = (!x||!y)? false : true;
    }
}
```

---


### 주사위 게임 3
![주사위 게임 3](https://github.com/yony-k/yony-k.github.io/assets/109204976/3b871548-0b3d-4ead-915e-b3236276d241)

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class Solution {
    public int solution(int a, int b, int c, int d) {
        int answer = 1;
        int[] arr = {a,b,c,d};
        
		Arrays.sort(arr);
		
		int[] dice = new int[6];
		
		for(int i=0;i<arr.length;i++) {
			dice[arr[i]-1]++;
		}
		
		for(int i=0;i<dice.length;i++) {
			if(dice[i]==4) {
				answer = 1111*(i+1);
				break;
			} else if(dice[i]==3) {
				if(arr[0]==arr[1]) {
					answer = (10 * arr[0] + arr[3])*(10 * arr[0] + arr[3]);
				} else {
					answer = (10 * arr[3] + arr[0])*(10 * arr[3] + arr[0]);
				}
			} else if(dice[i]==2) {
				for(int j=0;j<dice.length;j++) {
					if(dice[j]==2) {
						if(i==j) continue;
						else answer =((i+1)+(j+1))*Math.abs((i+1)-(j+1));
						break;
					} else if(dice[j]==1) {
						answer *= (j+1);
					}
				}
			}	
		}

		if(arr[0]!=arr[1]&&arr[1]!=arr[2]&&arr[2]!=arr[3]) {
			answer = arr[0];
		}
		
		return answer;
    }
}
```

---


### 글자 이어 붙여 문자열 만들기
![글자 이어 붙여 문자열 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a0e6bad8-bb34-41f3-836b-1fe399baf3b5)

```java
class Solution {
    public String solution(String my_string, int[] index_list) {
        String answer = "";
        
        for(int i : index_list) {
        	answer += my_string.charAt(i);
        }
        
        return answer;
    }
}
```

---


### 9로 나눈 나머지
![9로 나눈 나머지](https://github.com/yony-k/yony-k.github.io/assets/109204976/0de3d262-ed92-485f-a25b-9d3325fae23e)

```java
class Solution {
    public int solution(String number) {
        int answer = 0;
        
        for(int i=0;i<number.length();i++) {
			answer += Character.getNumericValue(number.charAt(i));
		}
        
        return answer%9;
    }
}
```

---


### 문자열 여러번 뒤집기
![문자열 여러 번 뒤집기](https://github.com/yony-k/yony-k.github.io/assets/109204976/caba92ac-e6de-4718-ae6b-4898d7491e44)

```java
class Solution {
    public String solution(String my_string, int[][] queries) {
        
        String answer = "";
        
        char[] ch = my_string.toCharArray();
		
		for(int i=0;i<queries.length;i++) {
			int s = queries[i][0];
			int e = queries[i][1];
			
			for(int j=s,k=e;j<=k;j++,k--) {
				char tmp = ch[j];
				ch[j] = ch[k];
				ch[k] = tmp;
			}
		}
		
		return answer = new String(ch);
    }
}
```
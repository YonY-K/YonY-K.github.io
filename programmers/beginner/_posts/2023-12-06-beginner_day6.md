---
title: "문자열, 반복문, 출력, 배열, 조건문"
tag: beginner
---

### 문자열 뒤집기
![문자열 뒤집기](https://github.com/yony-k/yony-k.github.io/assets/109204976/ce11590a-7097-4aa5-bbbb-acc6326f0d56)

```java
class Solution {
    public String solution(String my_string) {
        String answer = "";
        
        for(int i=my_string.length()-1;i>=0;i--) {
			answer += my_string.charAt(i);
		}
        
        return answer;
    }
}
```

---

### 직각삼각형 출력하기
![직각삼각형 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/1686e438-fc85-4021-beef-26c5cd955052)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        for(int i=0;i<n;i++) {
			for(int j=0;j<=i;j++) {
				System.out.print("*");
			}
			System.out.println();
		}
    }
}
```

---

### 짝수 홀수 개수
![짝수 홀수 개수](https://github.com/yony-k/yony-k.github.io/assets/109204976/8d9aeef7-730b-4b0f-93fd-88a6ca03fe82)

```java
class Solution {
    public int[] solution(int[] num_list) {
        int even=0;
		int odd=0;

		for(int i=0;i<num_list.length;i++) {
			if(num_list[i]%2==0) even++;
			else odd++;
		}
		
		int[] answer = {even,odd};
        return answer;
    }
}
```

---

### 문자 반복 출력하기
![문자 반복 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/5515bb2a-2eb2-4645-abf7-bf57069cc63f)

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        
        for(int i=0;i<my_string.length();i++) {
			for(int j=0;j<n;j++) {
				answer += my_string.charAt(i);
			}
		}
        
        return answer;
    }
}
```


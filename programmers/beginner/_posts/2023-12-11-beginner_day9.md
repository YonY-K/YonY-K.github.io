---
title: "수학, 문자열, 해시, 완전탐색, 조건문"
tag: beginner
---

### 개미 군단![개미 군단](https://github.com/yony-k/yony-k.github.io/assets/109204976/3d78f88c-26ae-4e6a-8a1c-ba4ca5d678fb)

```java
class Solution {
    public int solution(int hp) {
        int answer = 0;
        
        while(hp>0) {
			if(hp>=5) {
				answer+=hp/5;
				hp = hp%5;
			} else if(hp>=3) {
				answer+=hp/3;
				hp = hp%3;
			} else {
				answer+=hp/1;
				hp-=hp/1;
			}
		}
        
        return answer;
    }
}
```
- hp를 먼저 5로 나누고 그 나머지를 3으로 나누고 또 나머지가 나온다면 1로 나눠주면 되었던 간단한 문제
- 나는 while문을 돌면서 hp를 계속 확인하며 나누어줬는데 굳이 확인할 필요없이 5로 나머지 연산 -> 3으로 나머지 연산 -> 1로 나머지 연산을 해주면 끝이었다.

---

### 모스부호 (1)
![모스부호 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/c5b7b829-347b-4eaa-b449-ff617710ad1f)
![모스부호 (1) 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/4d5f6197-9708-4b7c-89a6-19ccfb05a300)

```java
class Solution {
    public String solution(String letter) {
        String answer = "";
        
        String[] arr = letter.split(" ");
		
		
		for(int i=0;i<arr.length;i++) {
			if (arr[i].equals(".-")) answer += "a";
			if (arr[i].equals("-...")) answer += "b";
			if (arr[i].equals("-.-.")) answer += "c";
			if (arr[i].equals("-..")) answer += "d";
			if (arr[i].equals(".")) answer += "e";
			if (arr[i].equals("..-.")) answer += "f";
			if (arr[i].equals("--.")) answer += "g";
			if (arr[i].equals("....")) answer += "h";
			if (arr[i].equals("..")) answer += "i";
			if (arr[i].equals(".---")) answer += "j";
			if (arr[i].equals("-.-")) answer += "k";
			if (arr[i].equals(".-..")) answer += "l";
			if (arr[i].equals("--")) answer += "m";
			if (arr[i].equals("-.")) answer += "n";
			if (arr[i].equals("---")) answer += "o";
			if (arr[i].equals(".--.")) answer += "p";
			if (arr[i].equals("--.-")) answer += "q";
			if (arr[i].equals(".-.")) answer += "r";
			if (arr[i].equals("...")) answer += "s";
			if (arr[i].equals("-")) answer += "t";
			if (arr[i].equals("..-")) answer += "u";
			if (arr[i].equals("...-")) answer += "v";
			if (arr[i].equals(".--")) answer += "w";
			if (arr[i].equals("-..-")) answer += "x";
			if (arr[i].equals("-.--")) answer += "y";
			if (arr[i].equals("--..")) answer += "z";
		}
        
        return answer;
    }
}
```

---

### 가위 바위 보
![가위 바위 보](https://github.com/yony-k/yony-k.github.io/assets/109204976/6b9c6266-132e-4d3b-812c-3b07709c7e11)

```java
class Solution {
    public String solution(String rsp) {
        String answer = "";
        
        String[] sp = rsp.split("");
		
		for(String s : sp) {
			if(s.equals("2")) answer+=0;
			else if(s.equals("0")) answer+=5;
			else answer+=2;
		}
        return answer;
    }
}
```

---

### 구슬을 나누는 경우의 수
![구슬을 나누는 경우의 수](https://github.com/yony-k/yony-k.github.io/assets/109204976/8a694c9c-da27-430c-9ce1-13148584b345)

```java
import java.math.BigInteger;

class Solution {
    public BigInteger solution(int balls, int share) {
        
        BigInteger a = factorial(balls);
		BigInteger b = factorial(balls-share);
		BigInteger c = factorial(share);
		BigInteger answer = a.divide(b.multiply(c));
        
        return answer;
    }
    
    static BigInteger factorial(int n) {
		if(n==1 || n==0) {
			return new BigInteger("1");
		}
		
		return new BigInteger(String.valueOf(n)).multiply(factorial(n-1));
	}
}
```

- 순열과 조합에 대해 알수 있었던 문제
- 이 개념에 대해서는 더 공부가 필요하다.
- 팩토리얼 계산 시 long으로도 감당할 수 없는 범위의 숫자가 나와서 BigInteger로 처리했다.
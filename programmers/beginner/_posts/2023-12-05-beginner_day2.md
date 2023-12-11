---
title: "사칙연산, 조건문, 배열"
tag: beginner
---

### 두 수의 나눗셈
![두 수의 나눗셈](https://github.com/yony-k/yony-k.github.io/assets/109204976/7347d53f-bf15-425e-91ad-b1e783dc8251)

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        return answer=(int)((num1/(double)num2)*1000);
    }
}
```

---

### 숫자 비교하기
![숫자 비교하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/9f7ea264-37dd-455d-b32f-c866221f1ccf)

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        return answer = num1==num2?1:-1;
    }
}
```

---

### 분수의 덧셈
![분수의 덧셈](https://github.com/yony-k/yony-k.github.io/assets/109204976/628609d7-9d47-43cf-9ee0-9372ed31882d)

```java
class Solution {
    public int[] solution(int numer1, int denom1, int numer2, int denom2) {
        int[] answer = new int[2];
		
		int denom3 = denom1*denom2;
		int numer3 = (numer1*denom2)+(numer2*denom1);
		int max=0;
		
		for(int i=1;i<=numer3&&i<=denom3;i++) {
			if(numer3%i==0&&denom3%i==0) {
				max = i;
			}
		}
		
		answer[0]=numer3/max;
		answer[1]=denom3/max;
        
        return answer;
    }
}
```

- 분수의 덧셈은 분모를 통분하면서 시작한다.
- 기약분수는 분자와 분모가 1 이외의 공통된 약수로 더이상 나누어떨어지지 않는 상태를 말한다.
- 기약분수를 구하려면 분자와 분모를 공통된 약수로 나누어야하는데 그 중 가장 큰수인 최대공약수로 나누면 단숨에 기약분수를 만들 수 있다.
- 최대공약수를 구하기 위해서는 여러가지 방법이 있다.
    1. 1부터 시작해서 분자와, 분모까지 수를 하나씩 높여가며 분자와 분모가 모두 나누어떨어지는 가장 큰 수를 방법
    2. 유클리드 호제법을 사용하여 먼저 분자와 분모를 나눠 나머지를 구한 후 그 나머지를 또 다시 나머지와 나눠 나머지를 구하는 식으로 나머지가 0이 될때까지 반복하여 최종적으로 나머지가 0이 되는 나머지를 구하는 방법

---

### 배열 두배 만들기
![배열 두배 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/23347855-3f10-437c-95da-fdfaddc1640a)

```java
class Solution {
    public int[] solution(int[] numbers) {
        int[] answer = {};
        
        for(int i=0;i<numbers.length;i++) {
            numbers[i] = numbers[i]*2;
        }
        
        return answer=numbers.clone();
    }
}
```


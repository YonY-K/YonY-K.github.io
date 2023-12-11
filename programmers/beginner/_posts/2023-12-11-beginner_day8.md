---
title: "배열, 구현, 수학"
tag: beginner
---

### 배열 자르기
![배열 자르기](https://github.com/yony-k/yony-k.github.io/assets/109204976/ac6bb743-9fc1-4ffa-8554-dbcfeabf68bc)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = Arrays.copyOfRange(numbers, num1, num2+1);
        return answer;
    }
}
```

- 특정 부분만을 복사하는 메소드가 있었다.
- Arrays.copyOfRange(복사하고픈 배열, 시작 위치, 끝 위치)

---

### 외계행성의 나이
![외계행성의 나이](https://github.com/yony-k/yony-k.github.io/assets/109204976/764b2390-5346-4399-ae90-9345d6b102df)

```java
class Solution {
    public String solution(int age) {
        String answer = "";
        
        String[] alp = {"a","b","c","d","e","f","g","h","i","j"};
		String str = String.valueOf(age);
		String[] arr = str.split("");
		
		for(int i=0;i<arr.length;i++) {
			answer += alp[Integer.parseInt(arr[i])];
		}
        
        return answer;
    }
}
```

- 알파벳 배열을 만들어서 나이를 위치값으로 사용해 answer에 더해줬다.

---

### 진료 순서 정하기
![진료 순서 정하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/bb992962-3710-480d-827a-cbd67f656a3d)

```java
import java.util.*;

class Solution {
    public int[] solution(int[] emergency) {
        int[] answer = Arrays.copyOf(emergency,emergency.length);
		
		int[] sort = Arrays.stream(emergency)
				.boxed()
				.sorted(Comparator.reverseOrder())
				.mapToInt(i->i.intValue()).toArray();
		
		for(int i=0;i<sort.length;i++) {
			for(int j=0;j<emergency.length;j++) {
				if(sort[i]==emergency[j]) answer[j]=i+1;
			}
		}
        
        return answer;
    }
}
```

- 매개변수 배열을 복사한 answer 배열
- 매개변수 배열의 순서를 내림차순으로 정렬한 sort 배열
- for문을 돌면서 sort 배열의 원소와 매개변수 배열의 원소가 일치하는 위치값을 찾아서 answer 배열에 넣어줬다.

---

### 순서쌍의 개수
![순서쌍의 개수](https://github.com/yony-k/yony-k.github.io/assets/109204976/c18efe28-3181-48d3-8014-289d2f9cdf0b)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        
        for(int i=1;i*i<=n;i++) {
        if(i*i==n) answer++;
        else if((n%i)==0) answer+=2;
		}
        
        return answer;
    }
}
```

- 약수를 찾아내는 문제였다.
1. 가장 간단하게 1부터 시작해서 n까지 n으로 나눠서 나머지가 0인지 확인하는 방법
2. 제곱근은 곱했을 때 n이 되는 숫자이니 이를 이용하여 for문을 제곱근까지만 돌도록 하여 시간을 단축하는 방법
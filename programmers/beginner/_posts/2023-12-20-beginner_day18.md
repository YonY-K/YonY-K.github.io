---
title: "문자열, 수학, 조건문, 정렬"
tag: beginner
---

### 문자열안에 문자열
![문자열안에 문자열](https://github.com/yony-k/yony-k.github.io/assets/109204976/18db308f-4a2e-4178-b4ae-8854c7c68841)

```java
class Solution {
    public int solution(String str1, String str2) {
        int answer = 0;
        answer = str1.contains(str2)?1:2;
        return answer;
    }
}
```

---

### 제곱수 판별하기
![제곱수 판별하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/c558eabd-40a7-4f31-8282-2feb12dfd709)

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        answer = Math.sqrt(n)%1.0==0.0?1:2;
        return answer;
    }
}
```

---

### 세균 증식
![세균 증식](https://github.com/yony-k/yony-k.github.io/assets/109204976/5501fd9c-1202-4938-82ad-8b5bded2d886)

```java
class Solution {
    public int solution(int n, int t) {
        int answer = n;
		
		int cnt=0;
		while(cnt<t) {
			answer *= 2;
			cnt++;
		}
        return answer;
    }
}
```

---

### 문자열 정렬하기 (2)
![문자열 정렬하기 (2)](https://github.com/yony-k/yony-k.github.io/assets/109204976/3c48201b-832e-407c-91b6-e48da5ba2c85)

```java
import java.util.*;
import java.util.stream.*;

class Solution {
    public String solution(String my_string) {
        String answer = "";
        answer = Arrays.stream(my_string.toLowerCase().split(""))
            .sorted()
            .collect(Collectors.joining());
        return answer;
    }
}
```


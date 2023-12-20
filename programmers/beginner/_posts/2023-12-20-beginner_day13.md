---
title: "문자열, 배열, 사칙연산, 수학, 조건문"
tag: beginner
---

### 컨트롤 제트
![컨트롤 제트](https://github.com/yony-k/yony-k.github.io/assets/109204976/68584936-cbdc-451c-9460-7862cab18339)

```java
class Solution {
    public int solution(String s) {
        int answer = 0;
        
        String[] sp = s.split(" ");
		
		int tnum=0;
		
		for(String n : sp) {
			if(n.equals("Z")) {
				answer -= tnum;
			} else {
				tnum = Integer.parseInt(n);
				answer += tnum;
			}
		}
        
        return answer;
    }
}
```

---

### 배열 원소의 길이
![배열 원소의 길이](https://github.com/yony-k/yony-k.github.io/assets/109204976/adb1a127-bbf6-4603-a206-877ed50b4e1e)

```java
import java.util.*;

class Solution {
    public int[] solution(String[] strlist) {
        int[] answer = {};
        
        List<Integer> list = new ArrayList<Integer>();
		
		for(String s : strlist) {
			list.add(s.length());
		}
		
		answer = list.stream().mapToInt(i->i.intValue()).toArray();
        
        return answer;
    }
}
```

---

### 중복된 문자 제거
![중복된 문자 제거](https://github.com/yony-k/yony-k.github.io/assets/109204976/5031b777-6b37-48ed-a545-b582dcd413d7)

```java
import java.util.*;
import java.util.stream.*;


class Solution {
    public String solution(String my_string) {
        String answer = Arrays.stream(my_string.split("")).distinct().collect(Collectors.joining());
        return answer;
    }
}
```

---

### 삼각형의 완성조건 (1)
![삼각형의 완성조건 (1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/989f20ec-bc9c-4a12-a254-55847cf670df)

```java
import java.util.*;

class Solution {
    public int solution(int[] sides) {
        int answer = 2;
        
        sides = Arrays.stream(sides).sorted().toArray();
		if(sides[2]<sides[0]+sides[1]) answer = 1;
        
        return answer;
    }
}
```


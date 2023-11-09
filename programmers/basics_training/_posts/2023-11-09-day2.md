---
title: "Day 2 출력, 연산"
tag: basics_training
---
### 덧셈식 출력하기
![덧셈식 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/f99f7975-0514-404a-8988-05923de967a7)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println(a +" + "+b+" = "+ (a+b));
    }
}
```

---
### 문자열 붙여서 출력하기
![문자열 붙여서 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/7872f4b9-2883-4251-a900-de323fdb3979)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        String b = sc.next();
        String c = a.trim()+b.trim();
        
        
        System.out.println(c);
            
    }
}
```
- 공백으로 구분되어 입력된 값이 코드창에서 자동으로 나누어져있어 더해서 출력하기만 하면 됐던 문제

---
### 문자열 돌리기
![문자열 돌리기](https://github.com/yony-k/yony-k.github.io/assets/109204976/3b876490-a687-4439-aa35-5a6b7be3c3a1)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        for(int i=0;i<a.length();i++) {
            System.out.println(a.charAt(i));
        }
    }
}
```

---
### 홀짝 구분하기
![홀짝 구분하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/64b56426-2527-4eee-9935-58e8eae92fc6)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        if(n%2==0){
            System.out.printf("%d is even",n);
        } else {
            System.out.printf("%d is odd",n);
        }
    }
}
```

---
### 문자열 겹쳐쓰기
![문자열 겹쳐쓰기](https://github.com/yony-k/yony-k.github.io/assets/109204976/6bada9bc-348a-4192-9db0-47986ca1d4af)

```java
class Solution {
    public String solution(String my_string, String overwrite_string, int s) {
        
		int l1 = my_string.length();
        int l2 = overwrite_string.length();

        String answer = my_string.substring(0,s)+ overwrite_string + my_string.substring(s+l2,l1);

        return answer;
    }
}
```
- .subString 메소드를 사용해서 문자를 잘라서 다시 붙여주는 방식
- 1. 기존 문자열의 시작위치부터 s위치 전까지 자르기
- 2. s 위치+바꿔야할 문자열 길이 전까지 자르기
- 3. 1과 바꿔야할 문자열, 2를 더해준다
- ex) He&nbsp;&nbsp;&nbsp;&nbsp;lloWorl&nbsp;&nbsp;&nbsp;&nbsp;d


<br>

- **.replace("기존 문자","바꾸고 싶은 문자")** : String에서 사용가능한 메소드로 기존 문자를 바꾸고 싶은 문자로 치환해주는 메소드, 정규식 사용가능
- **.replaceAll("기존 문자","바꾸고 싶은 문자")** : 위 메소드와 똑같은 기능이지만 정규식 사용 불가
- **.replaceFirst("기존 문자","바꾸고 싶은 문자")** : 한 문자열에 바꾸고 싶은 기존 문자가 여러개일 수 있는데 이중에서 첫번째 문자만 바꾸고 싶은 문자로 바꿔준다.
- **.substring(int(시작), int(끝,포함x))** : 시작 위치에서 끝 위치 전까지의 문자열을 잘라오는 메소드

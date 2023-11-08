---
title: "대문자-소문자 변환 과제"
tag: study_homework
---

### 문제
키보드로 문자열을 받았을 떄 대문자이면 소문자로, 소문자이면 대문자로 바꿔서 출력하기(ASbs->asBS)<br>
단, 특수문자나 한글, 숫자일 때는 "입력 값 오류"로 표기

```java
Scanner sc = new Scanner(System.in);
System.out.print("문자 입력: ");
String msg = sc.next();
String newmsg = "";

for(int i=0;i<msg.length();i++) {
    int ch = Character.codePointAt(msg, i);
    if(ch>=65&&ch<=90) { //대문자인 경우
        newmsg += (char)(ch+32);
    } else if(ch>=97&&ch<=122) {  //소문자인 경우
        newmsg += (char)(ch-32);
    } else {  //그 외의 경우
        System.out.println("입력 값 오류");
        break;
    }
    
    if(i==msg.length()-1) System.out.println(newmsg);
}
```


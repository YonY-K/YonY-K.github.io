---
title: "별찍기 과제"
tag: study_homework
---

### Q1. 
    *****

```java
String s = "";
for(int i=0;i<5;i++) {
    s += "*";
}

System.out.println(s);
```
<br>

### Q2.
    *
    *
    *
    *
    *

```java
//하나 찍고 줄 바꾸기
		
String s = "";
for(int i=0;i<5;i++) {
    s += "*\n";
}

System.out.println(s);
```
<br>

### Q3.

    ***** 
    *****
    *****
    ***** 
    *****

```java
//5개 찍고(루프1) 줄바꾸기(루프2)

String s = "";
for(int i=0;i<5;i++) {
    for(int j =0;j<5;j++) {
        s += "*";
    }
    s += "\n";
}

System.out.println(s);
```
<br> 

### Q4.
    *
    **
    ***
    ****
    *****

```java
//1개부터 시작해서 1개씩 추가됨
//별 찍고(루프1) 줄바꿈(루프2)
//i 변수는 별의 개수로 활용
//j 변수는 반복할 때만 활용

String s = "";
for(int i=1;i<=5;i++) {
    for(int j=0;j<i;j++) {
        s += "*";
    }
    s += "\n";
}

System.out.println(s);
```
<br>

### Q5.
    *****
    ****
    ***
    **
    *

```java
//가장 큰 숫자에서 시작해서 1씩 작아짐
//안쪽 for문에서 i 변수만큼 별을 찍어주는 건 동일
//바깥쪽 for문에서 i가 큰 수에서 시작하기 때문에 조건문의 조건을 바꿔줘야함

String s = "";
for(int i=5;i>=1;i--) {
    for(int j=0;j<i;j++) {
        s += "*";
    }
    s += "\n";
}

System.out.println(s);
```
<br> 

### Q6.
    *****
     ****
      ***
       **
        *


```java
//별과 스페이스가 같이 찍힘
//줄바꿈(루프1), 별찍기(루프2-1), 스페이스찍기(루프2-2)
//별이 큰수에서 시작하고 스페이스는 1부터 시작함

String s = "";
for(int i=1,space=0,star=5;i<=5;i++,space++,star--) {
    //스페이스 찍기
    for(int j=0;j<space;j++) {
        s += " ";
    }
    //별 찍기
    for(int k=0;k<star;k++) {
        s += "*";
    }
    //줄바꿈
    s += "\n";
}

System.out.println(s);
```
<br>

### Q7.
        *
       **
      ***
     ****
    *****


```java
//스페이스가 큰수에서 시작, 별이 1에서 시작
//스페이스가 1씩 감소, 별이 1씩 증가

String s = "";
for(int i=1,space=4,star=1;i<=5;i++,space--,star++) {
    //스페이스 찍기
    for(int j=0;j<space;j++) {
        s += " ";
    }
    //별찍기
    for(int k=0;k<star;k++) {
        s += "*";
    }
    //줄바꿈
    s += "\n";
}

System.out.println(s);
```
<br>

### Q8. 
	*
	**
	***
	****
	*****
	****
	***
	**
	*	



```java
//별이 1부터 시작해서 1씩 증가
//별이 5가 되면 1씩 감소
//별 찍고(루프1) 줄 바꿈(루프2)

String s = "";
for(int i=1,plus=1;i>0;i+=plus) {
    for(int j=0;j<i;j++) {
        s += "*";
    }
    if(i==5) plus=-1;
    s+="\n";
}
System.out.println(s);
```
<br>

### Q9.
    *****
    ****
    ***
    **
    *
    **
    ***
    ****
    ***** 

```java
//별이 큰수에서 시작해서 1씩 감소
//별이 1이 되면 1씩 증가
//별이 5보다 커지면 끝

String s = "";
for(int i=5,plus=-1;i<=5;i+=plus) {
    for(int j=0;j<i;j++) {
        s += "*";
    }
    if(i==1) plus=1;
    s+="\n";
}
System.out.println(s);
```    
<br>

### Q10.
        *
       **
      ***
     ****
    *****
     ****
      ***
       **
        *

```java
//스페이스와 별이 함께 찍힘
//스페이스가 큰수에서 시작 1씩 감소, 별이 1에서 시작 1씩 증가
//별이 5가 되면 스페이스가 1씩 증가, 별이 1씩 감소
//별이 1보다 작아지면 끝

String s = "";
for(int space=4,star=1,plus1=-1,plus2=1;star>0;space+=plus1,star+=plus2) {
    for(int j=0;j<space;j++) {
        s += " ";
    }
    for(int k=0;k<star;k++) {
        s += "*";
    }
    if(star==5) {
        plus1=1;
        plus2=-1;
    }
    s+="\n";
}
System.out.println(s);
```
<br>

### Q11.
        *
       ***
      *****
     *******
    *********	

```java
//스페이스가 큰수, 별이 1에서 시작
//스페이스가 1씩 감소, 별이 2씩 증가
//스페이스가 0보다 작아지면 끝

String s = "";
for(int space=4,star=1;space>=0;space--,star+=2) {
    for(int j=0;j<space;j++) {
        s += " ";
    }
    for(int k=0;k<star;k++) {
        s += "*";
    }
    s+="\n";
}
System.out.println(s);
```
<br>

### Q12.
    *********
     *******
      *****
       ***
        *  

```java
//스페이스가 0에서 시작, 별이 큰수에서 시작
//스페이스가 1씩 증가, 별이 2씩 감소
//별이 0보다 작아지면 끝

String s = "";
for(int space=0,star=9;star>0;space++,star-=2) {
    for(int j=0;j<space;j++) {
        s += " ";
    }
    for(int k=0;k<star;k++) {
        s += "*";
    }
    s+="\n";
}
System.out.println(s);
```
<br>

### Q13.
        *  
       ***  
      *****
     *******
    *********
     *******
      *****
       ***
        *

```java
//스페이스 4에서 시작, 별 1에서 시작
//스페이스 1씩 감소, 별은 2씩 증가
//스페이스가 0이 되면 스페이스 1씩 증가, 별이 2씩 감소
//별이 0보다 작아지면 끝

String s = "";
for(int space=4,star=1,plus1=-1,plus2=2;star>0;space+=plus1,star+=plus2) {
    for(int j=0;j<space;j++) {
        s += " ";
    }
    for(int k=0;k<star;k++) {
        s += "*";
    }
    if(space==0) {
        plus1=1;
        plus2=-2;
    }
    s+="\n";
}
System.out.println(s);
```
<br>

### Q14.
    ***** *****
    ****   ****
    ***     ***
    **       **
    *         *
    **       **
    ***     ***
    ****   ****
    ***** *****

```java
//별 찍기-스페이스 찍기-별 찍기 
//별이 5에서 시작, 스페이스가 1에서 시작
//별이 1씩 감소, 스페이스가 2씩 증가
//별이 1이 되면 별이 1씩 증가, 스페이스가 2씩 감소
//스페이스가 0보다 작아지면 끝

String s = "";
for(int space=1,star=5,plus1=2,plus2=-1;space>0;space+=plus1,star+=plus2) {
    for(int j=0;j<star;j++) {
        s += "*";
    }
    for(int j=0;j<space;j++) {
        s += " ";
    }
    for(int j=0;j<star;j++) {
        s += "*";
    }
    if(star==1) {
        plus1=-2;
        plus2=1;
    }
    s+="\n";
}
System.out.println(s);
```
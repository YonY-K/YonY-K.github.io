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
\* <br> 
\** <br> 
\*** <br> 
\**** <br> 
\***** <br> 

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
\***** <br> 
\**** <br> 
\*** <br> 
\** <br> 
\* <br> 

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
<br>

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
<br>

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

<br>

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
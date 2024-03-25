---
title: programmers Lv.1
author: The journey is the reward
date:   2024-03-18 17:44:02 +09:00
categories: [programmers]
tags: [programmers]
---


> programmers Level별 풀이 블로그에 기록용입니다. 언어 : Java



# x만큼 간격이 있는 n개의 숫자
---

```java
class Solution {
    public long[] solution(int x, int n) {
        long[] answer = new long[n]; //n개의 길이의 배열 선언
        for(int i=0;i<n;i++) //입력한 변수의 길이만큼
        {
            answer[i] = (long)(i+1)*x; //answer 배열의 0번 인덱스부터 (i+1)*x값 반복
        }
        return answer;
    }
}
 
```
- 💡 제한조건 : x가 -10,000,000 이상 10,000,000 이하인 정수, n은  1,000 이하인 자연수

- x의 값이 10,000,000이고 n의 입력이 1,000일 경우 최대 출력 값은 10,000,000,000가 되고 int 형의 범위는 -2,147,483,648~2,147,483,647이므로 long 타입으로 형변환을 해야함.

```java
class Solution {
    public long[] solution(int x, int n) {
        long[] answer = new long[n];
        answer[0] = x;
        for(int i=1;i<n;i++)
        {
            answer[i] = answer[i-1]+x;
        }
        return answer;
    }
}

```

#  문자열을 정수로 바꾸기
---
```java
class Solution {
    public int solution(String s) {
        int answer = 0;
        answer = Integer.parseInt(s);
        return answer;
    }
}
```
```java
class Solution {
    public int solution(String s) {
        String answer = s;
        return Integer.parseInt(answer);
    }
}
```
#  자릿수 더하기
---
```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;
        String[] arr = String.valueOf(n).split("");
        for(String value : arr)
        {
            answer+=Integer.parseInt(value);
        }
        return answer;
    }
}
```

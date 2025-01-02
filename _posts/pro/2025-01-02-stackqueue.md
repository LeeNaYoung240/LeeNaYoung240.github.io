---
title: 💪🏻 programmers 고득점 Kit - 스택(Stack), 큐(Queue)
author: LeeNaYoung
date:   2025-01-02 17:33:02 +09:00
categories: [programmers]
tags: [programmers]
---

# 같은 숫자는 싫어 - 프로그래머스

배열에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하는 문제. 단, 배열 arr의 원소들의 순서를 유지해야 함.

1) `stack` 선언

2) `stack`에 값이 없고, `stack` 최상단의 값이 `arr` 배열 값이 아닐 때 `stack`에 삽입

3) 역순으로 결과 배열에 `stack` 값 `pop()`을 통해 출력

```java
import java.util.*;

public class Solution {
    public int[] solution(int []arr) {
      
        Stack<Integer> stack = new Stack<>();
        
        for(int i=0;i<arr.length;i++)
        {
            if(stack.empty() || stack.peek()!=arr[i])
            {
                stack.push(arr[i]);
            }
        }
        int[] answer = new int[stack.size()];
        
        for(int i=stack.size()-1;i>=0;i--)
        {
            answer[i] = stack.pop();
        }
    
        return answer;
    }
}
```

<br>

# 기능 개발 - 프로그래머스

기능 개선 작업을 수행 중이다. 각 기능은 진도가 100%일 때 서비스에 반영할 수 있다, 또, 각 기능의 개발 속도는 모두 다르기 때문에 뒤에 있는 기능이 앞에 있는 기능보다 먼저 개발될 수 있고, 이때 뒤에 있는 기능은 앞에 있는 기능이 배포될 때 함께 배포된다.
먼저 배포되어야 하는 순서대로 작업의 진도가 적힌 정수 배열 progresses와 각 작업의 개발 속도가 적힌 정수 배열 speeds가 주어질 때 각 배포마다 몇 개의 기능이 배포되는지를 구하는 문제.

1) `ArrayList`와 `Queue` 선언

2) 일 수를 구하기 위해 `100 - progresses[i]`를 한 뒤, `speeds[i]` 값으로 나눈다. 또 `2.XX`와 같은 경우가 있을 수 있으니 `Math.ceil`을 이용해 올림을 한다.

3) `queue` 값이 비지 않으면서 `queue`의 최상단의 값이 `date` 값 보다 작을경우 `List`에 `queue`의 크기를 삽입한다. 그 다음 `queue`를 초기화 한다.

4) `queue`에 `date` 값을 대입한다.

5) `answer` 배열의 길이를 `answerList.size()`로 선언한 뒤, 결과값에 `answerList.get(i)`를 대입한다.


-   작업들의 진행 상황: `progresses = [93, 30, 55]`
-   작업 속도: `speeds = [1, 30, 5]`

----------


1.  첫 번째 작업:
    
    -   남은 작업량: `100 - 93 = 7`
    -   완료 날짜: `7 / 1 = 7`일
    -   큐 상태: `q = [7]` (첫 번째 작업의 완료 날짜)
2.  두 번째 작업:
    
    -   남은 작업량: `100 - 30 = 70`
    -   완료 날짜: `70 / 30 = 2.333...` → `Math.ceil(2.333...) = 3`일
    -   큐 상태: 현재 큐의 첫 번째 값(`q.peek() = 7`)과 비교:
        -   `7 > 3`이므로, 두 번째 작업은 첫 번째 작업과 함께 배포 가능.
        -   큐에 `3` 추가: `q = [7, 3]`
3.  세 번째 작업:
    
    -   남은 작업량: `100 - 55 = 45`
    -   완료 날짜: `45 / 5 = 9`일
    -   큐 상태: 현재 큐의 첫 번째 값(`q.peek() = 7`)과 비교:
        -   `7 < 9`이므로, 새로운 배포 그룹이 시작됨.
        -   **지금까지 큐에 쌓인 작업 수**(`q.size() = 2`)를 결과 리스트에 추가: `answerList = [2]`.
        -   큐 초기화: `q.clear()`.
        -   세 번째 작업의 완료 날짜 추가: `q = [9]`.

```java
import java.util.*;
class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
        ArrayList<Integer> answerList = new ArrayList<>();
        Queue<Integer> q = new LinkedList<>();
        
        for(int i=0;i<speeds.length;i++)
        {
            double remain = (100-progresses[i])/(double)speeds[i];
            int date = (int)Math.ceil(remain);
            
            if(!q.isEmpty() && q.peek() < date)
            {
                answerList.add(q.size());
                q.clear();
            }
            q.offer(date);
        }
        answerList.add(q.size());
        
        int[] answer = new int[answerList.size()];
        
        for(int i=0;i<answer.length;i++)
        {
            answer[i] = answerList.get(i);
        }
        
        return answer;
    }
}
```

<br>

# 올바른 괄호 - 프로그래머스

괄호가 바르게 짝지어졌다는 것은 `'('` 문자로 열렸으면 반드시 짝지어서 `')'` 문자로 닫혀야 한다는 뜻이다. 예를 들어

-   `"()()"` 또는 `"(())()"` 는 올바른 괄호이다.
-   `")()("` 또는 `"(()("` 는 올바르지 않은 괄호이다.

`'('` 또는 `')'` 로만 이루어진 문자열 `s`가 주어졌을 때, 문자열 `s`가 올바른 괄호이면 `true`를 `return` 하고, 올바르지 않은 괄호이면 `false`를 `return` 하는 함수를 구하기

1) `Character` 타입으로 `stack` 선언하기

2) 문자열 `s`에서 `s.charAt(i)`을 통해 한글자씩 추출하기

3) `'('` 해당 문자라면 `stack`에 `push`를 이용하여 삽입

4) `')'` 해당 문자라면 `stack`에 `pop`을 이용하여 빼기, 여기서 스택이 비었을 때(`isEmpty()`) 해당 문자가 들어온다면 `return false`

5) `return stack.isEmpty()`를 통해 모두 비었을 때 `true`, `stack`에 값이 남아있다면 `false`를 반환


```java
import java.util.*;
class Solution {
    boolean solution(String s) {
        boolean answer = true;

        Stack<Character> stack = new Stack<>();
        
        for(int i=0;i<s.length();i++)
        {
            if(s.charAt(i)=='(')
            {
                stack.push('(');
            }
            else if(s.charAt(i)==')')
            {
                if(stack.isEmpty())
                {
                    return false;
                }
                stack.pop();
            }
        }

        return stack.isEmpty();
    }
}
```

<br>

# 프로세스 - 프로그래머스

1) 우선순위 큐를 `내림차순`으로 선언

2) `priorities`를 `pq`에 저장

3) 큐가 비지 않을 때까지, `priorities`의 길이만큼 반복. 만약 `pq`의 최상단 값과 `priorites`의 해당 값이 같다면 큐에서 꺼내고 `answer`값 증가

4) `location`과 해당 인덱스의 값이 같다면 반환하기

```java
import java.util.*;
class Solution {
    public int solution(int[] priorities, int location) {
        int answer = 0;
        
        PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
        
        for(int i=0;i<priorities.length;i++)
        {
            pq.offer(priorities[i]);
        }
        
        while(!pq.isEmpty())
        {
            for(int i=0;i<priorities.length;i++)
            {
                if(pq.peek() == priorities[i])
                {
                    pq.poll();
                    answer++;
                    if(location == i)
                    {
                        return answer;
                    }
                }
            }
        }
        
        return answer;
    }
}
```

<br>

# 다리를 지나는 트럭 - 프로그래머스

```java
import java.util.*;
class Solution {
    public int solution(int bridge_length, int weight, int[] truck_weights) {
        int answer = 0;
        int size = truck_weights.length; //다리 위를 건너야 할 트럭의 수
        int current = 0; // 다리 위에 올라간 트럭 무게
        int idx = 0;
        
        Queue<Integer> q = new LinkedList<>();
        
        do{
            if(q.size() == bridge_length)
            {
                current -= q.poll(); // 다리 위에 트럭이 꽉 차면 다리를 건넌 트럭을 큐에서 제거하고 그 무게를 빼줌
            }
            if(idx<size && current + truck_weights[idx] <= weight) // 다리위에 트럭이 올라갈 수 있다면
            {
                q.add(truck_weights[idx]); // 큐에 해당 인덱스 번호의 무게를 추가
                current += truck_weights[idx++]; // 무게에 해당 무게를 추가
            }
            else
                q.add(0); // 트럭이 올라갈 수 없다면 0 추가
            
            answer++; // 시간 증가
            
        } while(current != 0); // 모든 트럭이 다리를 건널 때까지 반복
        
        
        return answer;
    }
}
```

<br>

# 주식가격 - 프로그래머스

|prices  |return  |
|--|--|
| [1, 2, 3, 2, 3] |[4, 3, 1, 1, 0]  |

첫 번째 가격 1은 2, 3, 2, 3보다 작으므로 가격이 떨어지지 않음 - 총 4초

두 번재 가격 2는 3, 2, 3 보다 작거나 같으므로 - 총 3초

세 번째 가격 3은 3이랑 같으므로 - 총 1초

네 번째 가격 2는 3보다 작으므로 - 총 1초

다섯 번째 가격 3은 비교 대상이 없으므로 - 총 0초

```java
import java.util.*;
class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];
        Queue<Integer> q = new LinkedList<>();
        
        for(int i : prices)
        {
            q.add(i);
        }
        int idx = 0;
        
        while(!q.isEmpty()) 
        {
            int currentPrice = q.poll(); // 첫번째 가격을 꺼냄
            for(int x : q) // 큐에 남아있는 가격들을 차례대로 확인
            {
                answer[idx]++; // 더 낮은 가격을 찾기 전까지 증가
                if(currentPrice > x) break;
            }
            idx++; // 다음 인덱스로
        }
        
        return answer;
    }
}
```
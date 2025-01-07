---
title: 💪🏻 programmers 고득점 Kit - 힙(Heap)
author: LeeNaYoung
date:   2025-01-07 11:36:02 +09:00
categories: [programmers]
tags: [programmers]
---

# Heap(힙)

**`최솟값`** 또는 **`최댓값`** 을 **`빠르게`** 찾아내기 위해 **`완전 이진트리`** 형태로 만들어진 자료구조

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/44a5c395-ac04-409b-9930-c37cee20cc44" class="popup img-link"><img src="https://github.com/user-attachments/assets/44a5c395-ac04-409b-9930-c37cee20cc44" alt="1" loading="lazy"></a>
이미지 출처 : [블로그 링크](https://foxtrotin.tistory.com/184)

`Tree 구조`, 거꾸로 보면 나무 같이 생겨서 트리구조라고 한다.

- `부모노드` : 자기 자신과 연결된 노드 중 자신보다 높은 노드`(B의 부모 : A)`

- `자식노드` : 자기 자신과 연결된 노드 중 자신보다 낮은 노드`(C의 자식 : G)`

- `루트노드` : 일명 뿌리 노드라고 하며 루트 노드는 하나의 트리에서 하나만 존재함 -> `A`

- `단말노드` : 리프 노드라고 하며 자식 노드가 없는 노드 

- `내부노드` : 단말 노드가 아닌 노드

- `형제노드` : 부모가 같은 노드 `(H, I, J)`

- `깊이(depth)` : 특정 노드에 도달하기 위해 거처가야 하는 '간선의 개수' `(H의 깊이 : A -> D -> H (2개))`

- `레벨(length)` : 특정 깊이에 있는 노드들의 집합

- `차수(degree)` : 특정 노드가 하위(자식) 노드와 연결된 개수 `(B의 차수 E, F (2개))`

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/1f62d39d-da86-48d2-ae5f-c7b22b028b48" class="popup img-link"><img src="https://github.com/user-attachments/assets/1f62d39d-da86-48d2-ae5f-c7b22b028b48" alt="1" loading="lazy"></a>
이미지 출처 : [블로그 링크](https://yoongrammer.tistory.com/69)

여기서 **`완전 이진 트리`** 란 위의 트리구조에서 특정한 형태로 제한을 하는 것이다.

- **모든 노드의 최대 차수를 2로 제한**한다. -> 각 노드는 자식 노드를 최대 2개까지만 가질 수 있다.

- '마지막 레벨'을 제외한 모든 노드가 채워져 있고 모든 노드는 왼쪽부터 채워져 있어야 한다.

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/0081826c-dfad-4208-a02b-73656113eece" class="popup img-link"><img src="https://github.com/user-attachments/assets/0081826c-dfad-4208-a02b-73656113eece" alt="1" loading="lazy"></a>
이미지 출처 : [블로그 링크](https://yoongrammer.tistory.com/69)

`포화 이진트리` : `마지막 레벨`을 제외한 모든 노드는 두 개의 자식 노드를 가져야 한다.

그렇다면 Heap(힙)의 구현은?

어떤 리스트에 값을 넣거나 빼려고 할 때, 우선순위가 높은 것부터 빼내려고 한다면 보통 정렬을 생각할 것이다. 숫자가 낮을수록 우선순위가 높다고 가정할 때, 매번 새 원소가 들어올 때마다 이미 리스트에 있던 원소들과 비교하고 정렬해야 한다.

이와 같은 과정은 비효율적이다. 따라서 이와 같은 조건을 붙인다.

부모노드는 항상 자식노드보다 우선순위가 높다! 즉, 모든 요소를 고려하여 우선 순위를 정할 필요가 없어진다. 부모노드가 항상 우선순위가 높다는 조건만 만족시키면서 완전 이진 트리 형태로 채워나가면 된다.

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/1f62d39d-da86-48d2-ae5f-c7b22b028b48" class="popup img-link"><img src="https://github.com/user-attachments/assets/1f62d39d-da86-48d2-ae5f-c7b22b028b48" alt="1" loading="lazy"></a>
이미지 출처 : [블로그 링크](https://yoongrammer.tistory.com/69)

그렇다면 루트 노드(`여기서 1`)는 항상 우선순위가 높은 노드이다. 이러한 원리로 최대값이나 최솟값을 빠르게 찾아낼 수 있다는 장점(`시간 복잡도: O(1)`)과 함께 삽입, 삭제, 연산시에도 부모노드가 자식노드보다 우선순위만 높으면 되므로 결국 트리의 깊이만큼만 비교를 하면 되기 때문에 `O(logN)`의 시간복잡도를 가지게 된다.

추가로 부모노드와 자식노드의 관계만 신경쓰면 되기 때문에 형제간 우선순위는 고려되지 않는다. 이러한 정렬 상태를 '반정렬 상태', '느슨한 정렬 상태', '약한 힙'이라고 한다.

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/8497d4fc-eb5d-43af-86f4-2c47c86b7625"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/8497d4fc-eb5d-43af-86f4-2c47c86b7625"  alt="1"  loading="lazy"></a>

- 최소 힙 : 부모 노드 값(key 값) <= 자식 노드 값(key 값)

- 최대 힙 : 부모 노드 값(key 값) >= 자식 노드 값(key 값)

🔊 성질

1. 왼쪽 자식 노드의 인덱스 = 부모 노드의 인덱스 * 2
2. 오른쪽 자식 노드의 인덱스 = 부모 노드의 인덱스 * 2 + 1
3. 부모 노드의 인덱스 = 자식 노드의 인덱스 / 2

## Heap(힙) 구현


- 배열로 구현

- 인덱스 0을 사용하지 않음

- 부모-자식 사이 인덱스 관계

	- 인덱스 `i` 에서 부모 인덱스 : `i / 2`

	- 인덱스 `i` 에서 좌측 인덱스 : `i * 2`

	- 인덱스 `i` 에서 우측 인덱스 : `(i * 2) + 1`

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/1eb21cde-e8f4-4f5c-8358-dc36ae3a7dd2"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/1eb21cde-e8f4-4f5c-8358-dc36ae3a7dd2"  alt="1"  loading="lazy"></a>
<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/86e78fca-1cb2-4b2e-9ce3-e5577deb49e2"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/86e78fca-1cb2-4b2e-9ce3-e5577deb49e2"  alt="1"  loading="lazy"></a>


## 최대 힙으로 가정


### 삽입 연산

1. 마지막 위치에 노드 만들어서 삽입

2. 부모 노드보다 값이 작으면 끝

3. 부모 노드보다 값이 크면 부모 노드와 스위치

4. 2~3번 과정 최대 루트까지 반복

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/6742679a-9910-4a66-87ea-311b97fa84cf"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/6742679a-9910-4a66-87ea-311b97fa84cf"  alt="1"  loading="lazy"></a>


- 새로운 노드 9 삽입

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/68578a06-df85-49c0-9298-2087f6772bb4"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/68578a06-df85-49c0-9298-2087f6772bb4"  alt="1"  loading="lazy"></a>

- 부모 노드보다 값이 크므로 부모 노드와 스위치 

### 삭제 연산

1. 루트 노드 값 제거

2. 마지막 노드 값 루트로 옮기고 노드 삭제

3-1. 자식 노드보다 값이 크면 끝

3-2. 자식 노드보다 값이 작으면 스위치

4. 3번 과정 최대 리프까지 반복

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/20b20efb-07cd-4617-ba28-a1620430dbb2"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/20b20efb-07cd-4617-ba28-a1620430dbb2"  alt="1"  loading="lazy"></a>

- 루트 노드 값 10 제거

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/97f1d04d-2521-4402-91b6-d27e8a0d8d96"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/97f1d04d-2521-4402-91b6-d27e8a0d8d96"  alt="1"  loading="lazy"></a>
 
 - 마지막 노드 값 루트로 옮기고 노드 삭제

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/cd8a91ab-c439-4538-80bb-d2480479b2a4"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/cd8a91ab-c439-4538-80bb-d2480479b2a4"  alt="1"  loading="lazy"></a>

- 자식 노드보다 값이 작으므로 스위치

<a  href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/9c23ebd4-46ae-45e4-b592-e214e6d85467"  class="popup img-link"><img  src="https://github.com/user-attachments/assets/9c23ebd4-46ae-45e4-b592-e214e6d85467"  alt="1"  loading="lazy"></a>

- 자식 노드보다 값이 작으므로 스위치

## 자바에서 우선순위 큐

### 선언

- `new PriorityQueue<[type]>()`

	- `PriorityQueue<Integer> pq = new PriorityQueue<>();` // 오름차순

	- `PriorityQueue<Integer> pq = new PriorityQueue<Integer>(Collections.reverseOrder());` // 내림차순

### 삽입

- `add(E element)` : 큐 공간이 없어서 삽입 실패 시 `exception` 

- `offer(E element)` : 큐 공간이 없어서 삽입 실패 시 `null` 반환

### 삭제

- `poll()` : `front`에 위치한 원소 제거 후 반환, 큐 비었다면 `null` 반환

- `remove()` : `front`에 위치한 원소 제거 후 반환, 큐 비었다면 `exception` 

- `pq.removeIf(n -> (n % 2 == 0));` 
	
	- `pq : [1, 2, 3, 4, 5] -> pq : [1, 3, 5]`

- `remove(E element)` : 특정 원소 제거, 삭제하려는 원소 큐에 없으면 `false` 반환

- `removeAll(collection<?>)` : 파라미터로 준 컬렉션의 겹치는 원소를 제거 

### 접근

- `peek()` : 첫 번째 데이터 반환, 큐 비어있다면 null 반환

- `iterator()` : 데이터 지우지 않고 순회할 경우 사용

```java
//pq : [1, 3, 2]

Iterator<Integer> iter = pq.Iterator();
while(iter.hasNext()) {
	Integer i = iter.next();
	System.out.Print(i + " ");
}
// 출력 : 1 3 2
```

### 기타 

- `size()` : 사이즈

- `toArray()` : 큐에 저장된 데이터 배열로 가져옴

# 더 맵게 - 프로그래머스

우선순위 큐에서 poll을 2번하면 첫 번째 값은 가장 작은 값, 그 다음은 두 번째로 작은 값이 된다. 이 두 수를 계산하여 다시 우선순위 큐에 넣으면 된다.

이 구조에서 가장 작은 수가 K를 넘지 않으면 이 과정을 반복하여 값을 구하면 된다.


```java
import java.util.*;
class Solution {
    public int solution(int[] scoville, int K) {
        int answer = 0;
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        
        for(int scovilles : scoville)
        {
            pq.offer(scovilles);
        }
        
        while(pq.size() > 1 && pq.peek() < K)
        {
            int fir = pq.poll();
            int sec = pq.poll();
            int total = fir + (sec * 2);
            pq.add(total);
            answer++;
        }
        
        if(pq.peek() < K && pq.size() <= 1)
        {
            return -1;
        }
        
        return answer;
    }
}
```

<br>

# 디스크 컨트롤러 - 프로그래머스


```java
import java.util.*;
class Solution {
    public int solution(int[][] jobs) {
        int answer = 0; // 총 대기시간의 합을 저장
        int time = 0; // 현재 시간
        int idx = 0; // 현재 처리 중인 작업의 인덱스
        int len = jobs.length; // 작업의 개수
        
        Arrays.sort(jobs, (o1,o2) -> (o1[0]-o2[0])); // 요청 시간을 기준으로 오름차순 정렬
        
        PriorityQueue<int[]> pq = new PriorityQueue<>((o1,o2)-> o1[1]-o2[1]); // 소요 시간이 짧은 작업부터 처리 
        
        while(!pq.isEmpty() || idx < len) // 큐가 비어있지 않거나 처리해야 할 작업이 남아 있을 때까지
        {
            while(idx < len && jobs[idx][0] <= time) // 현재 시간보다 요청 시간이 작거나 같은 작업을 우선순위 큐에 추가
            {
                pq.offer(jobs[idx++]); // 작업을 큐에 넣고 idx 1 증가
            } 
            if(pq.isEmpty()) // 큐가 비었다면 다음 작업이 요청된 시점으로 시간 이동
            {
                time = jobs[idx][0];
            }
            else{
                int[] job = pq.poll();
                time += job[1];
                answer += time - job[0];
            }
        }
            
        return answer / len;
    }
}
```

<br>

# 이중우선순위큐 - 프로그래머스

```java
import java.util.*;
class Solution {
    public int[] solution(String[] operations) {
        int[] answer = {0,0};
        PriorityQueue<Integer> max = new PriorityQueue<Integer>(Collections.reverseOrder());
        PriorityQueue<Integer> min = new PriorityQueue<Integer>();
        
        for(int i=0;i<operations.length;i++)
        {
            String[] str = operations[i].split(" ");
            int num = Integer.valueOf(str[1]);
            if(str[0].equals("I"))
            {
                max.offer(num);
                min.offer(num);
            }
            else if(str[0].equals("D") && num == 1 && !max.isEmpty())
            {
                min.remove(max.poll());
            }
            else if(str[0].equals("D") && num == -1 && !min.isEmpty())
            {
                max.remove(min.poll());
            }
        }
        if(!min.isEmpty() && !max.isEmpty())
        {
            answer[0] = max.peek();
            answer[1] = min.peek();
        }
        
        return answer;
    }
}
```

# 참고 🙇🏻‍♀️


[블로그 - https://st-lab.tistory.com/205 ](https://st-lab.tistory.com/205)

[블로그 - https://velog.io/@suk13574/자료구조Java-힙heap ](https://velog.io/@suk13574/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0Java-%ED%9E%99heap)
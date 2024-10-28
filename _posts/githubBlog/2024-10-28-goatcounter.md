---
title: GitHub Blog - 페이지 조회수 추가하기(GoatCounter)
author: The journey is the reward
layout: post
categories: [GitHub Blog]
tags: [GitHub Blog, 페이지 조회수, GoatCounter]
date: 2024-10-28 19:47:02 +09:00
image:
    path: /assets/img/post/goatcounter.png
---

# GoatCounter

블로그를 운영하며 다른 사이트(tistory, 네이버 등) 블로그들은 조회수가 기본적으로 제공됩니다. 깃허브 블로그도 GoatCounter를 통해 조회수(본 사람 수)를 적용할 수 있습니다.


[GoatCounter 링크](https://www.goatcounter.com/)


해당 링크에 접속하여 회원가입을 진행합니다.


## 1. 회원가입


<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/0b9990b6-9eec-40ef-af78-a3bc32664170" class="popup img-link"><img src="https://github.com/user-attachments/assets/0b9990b6-9eec-40ef-af78-a3bc32664170" alt="1" loading="lazy"></a>

- Code : 원하는 서브도메인  (언더바는 허용 x)

- Site domain : 깃허브 블로그 주소

- Email address : 계정 검증용 이메일

- Password : 비밀번호

- Fill in 9 here : 9를 작성

<br>

## 2. 이메일 인증

<br>


## 3. 설정 - Settings

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/d409b1ea-44bb-4055-bfa7-4533a804ffaf" class="popup img-link"><img src="https://github.com/user-attachments/assets/d409b1ea-44bb-4055-bfa7-4533a804ffaf" alt="1" loading="lazy"></a>

- 웹 사이트에 방문자 수를 추가할 수 있도록 허용 버튼을 체크합니다. 

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/5c269728-8d6b-4aa2-a718-4612e840c07e" class="popup img-link"><img src="https://github.com/user-attachments/assets/5c269728-8d6b-4aa2-a718-4612e840c07e" alt="1" loading="lazy"></a>

- 특정 국가에서만 데이터를 수집하도록 설정하는 옵션입니다.

	- 이 필드를 비워두면 모든 국가에서 데이터를 수집하게 됩니다.

<br>

## 4. 코드 수정

`_config.yml` 위치에 가서 id 부분에 위에서 작성한 서브 도메인을 작성합니다.

```yml
analytics:
 google:
  id: 
 goatcounter: 
  id: 작성한 서브 도메인
```

`_config.yml` 위치에 `provider`에 `goatcounter`를 작성합니다.

```yml
# Page views settings
pageviews:
 provider: goatcounter
```

<br>

## 📌 참고

[참고한 블로그](https://blog.ju-ing.com/posts/jekyll-theme-chirpy-goatcounter/)
---
title: GitHub Blog 만들기 (1)
author: The journey is the reward
date:   2024-02-29 16:27:02 +09:00
categories: [GitHub Blog]
tags: [GitHub Blog]
---

# GitHub Blog 만들기 카테고리
---
[GitHub Blog 만들기 (1)](https://LeeNaYoung240.github.io/posts/2024-02-29-githubblog/)

[GitHub Blog 만들기 (2)](https://LeeNaYoung240.github.io/posts/2024-03-04-githubblog/)

[GitHub Blog 만들기 (3)](https://LeeNaYoung240.github.io/posts/2024-03-042-githubblog/)


# 시작
---
개발을 하다 보면 똑같은 오류를 직면할 때가 많지만 까먹게 되어 같은 오류라도 한참을 헤매는 경우가 번번했습니다. 이로 인해 블로그를 개설하여 작성하는 습관을 들이고자 "GitHub Blog"를 시작하게 되었습니다. 

Github Blog는 다른 블로그 사이트들에 비해 난이도가 높다고 생각합니다. (물론 제 기준..)  

제가 Github Blog를 선택한 이유는 backend 개발자를 목표로 하고 있고, backend 개발자라면 frontend에 대하여 이해도가 어느 정도 있어야 된다고 생각했습니다. 따라서 frontend의 파트인 CSS, HTML을 활용하여 블로그를 커스터마이징하여 포트폴리오로 활용하고자 합니다.

Github Blog를 만들면서 수 많은 오류에 직면하며 여러 자료들을 참고하였고 감사한 마음으로 다른 누군가에게 도움을 주고자 글을 작성합니다.


# 1. GitHub Blog란?
---
개발자는 다양한 사람과 협업을 통해 코드를 수정 및 추가, 삭제를 하며 개발합니다. 기록을 남겨두지 않으면 앞서 **시작**에서 말한 것처럼 까먹게 되어 헤매는 경우가 많아지고 빠른 대응이 어려워질 것입니다. 그래서 기록을 남기는 도구를 **Git** 이라고 부르며 이를 웹에서 볼 수 있도록 도와주는 서비스 중 하나를 **GitHub*라고 합니다. 

여기서 Github Page란 Github 저장소에 저장된 html 파일과 같은 정적 웹 문서들을 Github에서 무료로 웹에서 볼 수 있도록 호스팅 서비스를 제공해 주는 것입니다.  이를 이용하여 블로그를 만든 것이 **GitHub Blog**입니다.  


# 2. Github 가입 및 Repository 생성
---
먼저 Github 계정 생성을 하면 다음과 같이 좌측 상단의 Repository를 확인 할 수 있습니다.

![Desktop View](/assets/img/2024-02-29/1.PNG)
 

 우측에서 New라는 버튼을 클립합니다. 
 
 
 ![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/721aad96-c5b7-429b-b298-28cd618e631f)


사용자 페이지는 https://username.github.io와 같은 주소형식을 가집니다. 
프로젝트 페이지는 https://username.github.io/project_name 과 같은 주소형식을 가집니다.

Owner은 그대로 두고 Repository name에 사진과 같이 **username.github.io**을 입력합니다. 본인의 Owner을 username이라고 생각하시면 됩니다!
> 저의 경우 LeeNaYoung240.github.io 입니다.

Public, Add a README file 선택 후 Create Repository 을 클릭합니다.


# 3. 설정 방법
---

![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/5c945cfd-837f-486f-bbc0-2216b265d7b4)


상단의 사진과 같이 Repositories에 들어가면 username.github.io로 생성된 걸 볼 수 있습니다. 

생성된 리포지토리인  username.github.io를 클릭합니다. 

 
 ![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/5480ec1b-6a97-4405-95d0-78b265314b53)


그 후 Settings를 클릭합니다.


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/8e708572-5e95-4ef9-8d62-23e68fa06066)


Pages 클릭한 뒤 branch를 main으로  맞춘 뒤 저장합니다.


그러면 상단에 

![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/292c9c9c-007d-4f98-a25f-f3a7764a4b7e)


Github Page가 생성됩니다. (생성되는 시간은 -분 정도 걸릴 수 있습니다.)
> 상단의 사진과 같이 https://LeeNaYoung.github.io/ 로 보여지지 않고 (https://LeeNaYoung240.github.io/(Projectname)) 으로 보여진다면 #2번에서 했던 Owner이름과 repository명이 다르기 때문입니다.


# 이어서
---
지금까지 github page를 생성했고 다음은 Github Desktop과 VSCode, Jekyll, Ruby에 대해 설치 후 설정 방법을 살펴보겠습니다.

궁금하신 부분이나 괜찮으셨다면 댓글 부탁드려요💨
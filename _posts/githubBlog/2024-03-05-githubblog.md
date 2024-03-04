---
title: GitHub Blog 만들기 (3)
author: The journey is the reward
date:   2024-03-05 17:56:02 +09:00
categories: [GitHub Blog]
tags: [GitHub Blog]
---

# GitHub Blog 만들기 카테고리
---
[GitHub Blog 만들기 (1)](https://LeeNaYoung240.github.io/posts/2024-02-29-githubblog/)

[GitHub Blog 만들기 (2)](https://LeeNaYoung240.github.io/posts/2024-03-04-githubblog/)

[GitHub Blog 만들기 (3)](https://LeeNaYoung240.github.io/posts/2024-03-042-githubblog/)


# 6.  오류 해결
---

하지만 전 **"--- layout: home # Index page ---"**라는 오류에 직면하게 되었습니다.


![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/ea7b955f-deac-4de9-b45a-cce097f89b68)

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/16a5e32a-56a0-4bf3-a802-03164dcd0b0a)


Github Setting - Pages - Build and development 에서 Source를 Github Action으로 변경 후, Jekyll.yml 으로 커밋 후에 해결할 수 있었습니다.


> 혹은 Linux 기반의 플랫폼이 아닌 경우 bundle 명령어를 통해 Linux platform을 추가해야 된다고 합니다.
> ``` $ bundle lock --add-platform x86_64-linux ```
> 해당 명령어를 로컬에서 수행하고 git repo에 커밋한 이후 Git Action으로 설정한 후 Jekyll.yml을 커밋하면 정상적으로 수행된다고 합니다.

-> 다른 분들의 해결 방법으로 main 브런치에서 gh-pages 브런치로 바꾸어주면 해결된다고 하는데 전 생성되지 않아서 상기의 방법으로 해결했습니다.



# 7. 수정 작업
---

그 후,  repo에서 삭제하고 추가해야 할 목록이 있습니다.
> 삭제해야 할 항목
- ```Gemfile.lock``` 파일
- ```docs ``` 폴더 및 디렉토리 
- ```.travis.tml```파일
- ```_posts.docs```(.md 파일들이 있는데 보고 필요한 것만 남겨 두면 됩니다.)
- ```.github``` 폴더에서 ```workflows``` 폴더를 남겨두고 파일 전부를 지우면 됩니다.
- ```.github/workflows/```에서 ```commitlint.yml```과 ```page-deploy.yml.hook``` 외에 다 지우면 됩니다.
- ```page-deploy.yml.hook``` 파일의 ```.hook``` 을 지우면 됩니다.

> 추가해야 할 항목
- ```.github/workflows/pages-deploy.yml.hool``` 파일에서 마지막 ```hook``` 부분을 지워 ```.github/workflows/pages-deploy.yml``` 파일로 만들어 줍니다.
 
 ```.github/workflows/pages-deploy.yml``` 파일을 열어 


```ruby
name: 'Automatic  build'
 on:
 push:
     branches:
     - main          
     paths-ignore:
     - .gitignore
     - README.md
     - LICENSE
```

branches 부분을 main으로 수정해 줍니다.

마지막으로 윈도우 검색창에서 Start Command Prompt with Ruby를 실행합니다.

```
 cd D:\Git\LeeNaYoung240.github.io
 ```
 해당 명령어로 디렉터리를 이동해 줍니다.


```
 bundle exec jekyll serve
```

Jekyll 서버를 동작시킵니다.

정상적으로 모두 실행 되었다면 주소창에 <http://127.0.0.1:4000/> 또는 <http://localhost:4000/>로 접속해서 페이지를 확입합니다.

정상적으로 확인된다면 Github Desktop에 들어가 Commit to main 과 Push Origin을 진행합니다.

-분 후에 본인의 Github blog 주소에 접속하여 정상적으로 페이지가 보일 것입니다.

# 추가 
---


![Desktop View](/assets/img/2024-02-29/26.PNG)

Github blog에 포스팅을 작성했는데 Home 버튼에 아무 게시글이 뜨지 않는 경우 해결 방법입니다.


![Desktop View](/assets/img/2024-02-29/27.PNG)

```_layout/home.html``` 파일을 열고 ```for post in posts``` 부분을


![Desktop View](/assets/img/2024-02-29/28.PNG)

```for post in site.posts``` 로 변경하면 됩니다.


궁금하신 부분이나 괜찮으셨다면 댓글 부탁드려요💨💨
---
layout: post
title: GitHub Blog 만들기 (1)
date:   2024-02-29 16:27:02 +09:00
home: GitHub Blog 만들기 (1)
categories: [GitHub Blog, GitHub Blog 만들기 (1)]
tags: [GitHub Blog]
---
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

![Desktop View](./assets/img/2024-02-29/1.PNG)
 

 우측에서 New라는 버튼을 클립합니다. 
 
 
![Desktop View](/assets/img/2024-02-29/2.PNG)


사용자 페이지는 https://username.github.io와 같은 주소형식을 가집니다. 
프로젝트 페이지는 https://username.github.io/project_name 과 같은 주소형식을 가집니다.

Owner은 그대로 두고 Repository name에 사진과 같이 **username.github.io**을 입력합니다. 본인의 Owner을 username이라고 생각하시면 됩니다!
> 저의 경우 LeeNaYoung240.github.io 입니다.

Public, Add a README file 선택 후 Create Repository 을 클릭합니다.


# 3. 설정 방법
---

![Desktop View](/assets/img/2024-02-29/3.PNG)


상단의 사진과 같이 Repositories에 들어가면 username.github.io로 생성된 걸 볼 수 있습니다. 

생성된 리포지토리인  username.github.io를 클릭합니다. 

 
![Desktop View](/assets/img/2024-02-29/4.PNG)


그 후 Settings를 클릭합니다.


![Desktop View](/assets/img/2024-02-29/5.PNG)


Pages 클릭한 뒤 branch를 main으로  맞춘 뒤 저장합니다.


그러면 상단에 

![Desktop View](/assets/img/2024-02-29/6.PNG)


Github Page가 생성됩니다. (생성되는 시간은 -분 정도 걸릴 수 있습니다.)
> 상단의 사진과 같이 https://LeeNaYoung.github.io/ 로 보여지지 않고 (https://LeeNaYoung240.github.io/(Projectname)) 으로 보여진다면 #2번에서 했던 Owner이름과 repository명이 다르기 때문입니다.



# 4. 설치(Github Desktop, VSCode)
---

1) Github Desktop 설치 
GitHub Descktop은 Github 또는 기타 Git 호스팅 서비스에서 호스트 되는 파일을 사용하는 데 도움이 되는 무료 오픈 소스 애플리케이션입니다.  
><https://desktop.github.com/> 사이트에 접속하여, 프로그램을 다운 받습니다.

2) VSCode 설치
Visual Studio Code는 Microsoft에서 개발한 무료 오픈소스 코드 편집기입니다. 다양한 플랫폼에서 지원되며, 코드 편집을 비롯해서 개발 작업을 보다 쉽게 수행할 수 있는 기능들을 제공합니다.
> <https://code.visualstudio.com/download> 사이트에 접속하여, 프로그램을 다운 받습니다. 

두개의 설치를 완료했다면 원격지에 있는 Github Repository 를 로컬과 Clone 합니다.
-> Repository에 있는 파일을 Local로 가져오는 것입니다. 

Github Desktop을 실행하여 Github에 가입한 계정으로 로그인 합니다. 



![Desktop View](/assets/img/2024-02-29/7.PNG)


상단의 사진과 같이 Owner/username.github.o를 선택하고 clone합니다.


![Desktop View](/assets/img/2024-02-29/8.PNG)


상단의 사진에서 Local path는 해당 경로의 폴더에 인터넷에 있는 Repository와 연동됩니다.


![Desktop View](/assets/img/2024-02-29/9.PNG)


좌측 상단이 정확히 진행되었는지 확인 하고 Open in Visual Studio Code 버튼을 누릅니다.


![Desktop View](/assets/img/2024-02-29/10.PNG)


해당과 같이 VSCode가 열립니다. 그러면 좌측에 **ReadMe.md**라는 파일을 확인할 수 있습니다. 
username.github.io에 **index.html이라는 이름의 파일을 하나 생성합니다.
```html
<html>
	<body>
		Hello! This is the first page!
	</body>
</html>
```
해당 코드를 작성해 줍니다. 


![Desktop View](/assets/img/2024-02-29/11.PNG)


그 후,  Github Descktop에 들어오면 다음과 같이 변경 되어있을 것입니다.


![Desktop View](/assets/img/2024-02-29/12.PNG)


좌측 하단의 Commit to main 버튼을 눌러줍니다. 


![Desktop View](/assets/img/2024-02-29/13.PNG)


그 후, Push origin 버튼을 눌러주면 됩니다.
Github 홈페이지의 username.github.io Repository에서 README.me 파일과 index.html 파일이 확인되면 Push가 완료된 것입니다. 
> https://username.github.io 를 접속했을 때 화면에 **Hello! This is the first Page!**라고 보인다면 완료입니다.
> 

# 5. 설치(Jekyll, Ruby)
---

Jekyll, Ruby 설치 전에 테마를 먼저 고릅니다. 다양한 Jekyll Themes를 지원하는 페이지가 있으니 원하시는 테마를 선택하시면 됩니다. 저는 <https://github.com/cotes2020/jekyll-theme-chirpy> 해당 github의 테마를 사용했습니다.


![Desktop View](/assets/img/2024-02-29/14.PNG)


Code를 클린 한 뒤, Download Zip을 눌러 해당 압출폴더를 다운로드 합니다.



![Desktop View](/assets/img/2024-02-29/15.PNG)


그 후, 본인의 Github Blog가 저장된 폴더에 


![Desktop View](/assets/img/2024-02-29/16.PNG)

![Desktop View](/assets/img/2024-02-29/17.PNG)


다음과 같이 압축을 풀었습니다.  파일이 존재한다는 메시지가 뜬다면 덮어쓰기를 진행하면 됩니다.

다운 받은 파일을 수정하기 전에 Jekyll를 설치해야 됩니다. 다운 받은 파일은 Jekyll  기반으로 개발 되어있기 때문에 Jekyll을 설치하지 않을 경우 저희가 원하는 방식으로 테마를 수정할 수 없게 됩니다. Jekyll 테마를 설치하고 수정, 관리하기 위해서는 먼저 Ruby 개발 환경을 세팅해야 됩니다.


1)  Ruby 설치

Ruby를 설치하는 이유는 Jekyll이 Ruby로 만들어졌기 때문입니다.

><https://www.ruby-lang.org/en/downloads/>

![Desktop View](/assets/img/2024-02-29/18.PNG)


전 Ruby+Devkit 3.2.2-1 (x64)을 다운로드 받았습니다.

설치 후에 윈도우 검색창에서 Start Command Prompt with Ruby를 실행합니다.



![Desktop View](/assets/img/2024-02-29/19.PNG)


그 후에 본인의 username.github.io이 저장된 경로로 이동해줍니다. 
위치를 모른다면 

![Desktop View](/assets/img/2024-02-29/20.PNG)

다음과 같이 README.md 파일을 우클릭 후 **파일 탐색기에 표시** 버튼을 누르면 폴더 창을 통해 위치를 찾으면 됩니다.


```
 cd D:\Git\LeeNaYoung240.github.io
 ```
 

 cd 명령어는 디렉터리 변경의 준말로 디렉터리를 이동하라는 뜻입니다. 이동 후에 인코딩을 합니다.
 
```
 chcp 65001
 ```

 cmd 명령 프롬프트 창에서 UTF-8 인코딩 방식으로 작성된 파일 내용을 Console에 띄우려 할 때 한글 깨짐 현상이 발생합니다. cmd에서 기본적으로 사용하고 있는 인코딩 방식은 cp949이므로 해당 명령어를 입력합니다.
 
 명령어 입력 후에 **"Active code page:650001"**이라는 문자를 확인하면 정상적으로 진행된 것입니다.


2) Jekyll 설치 

- Jekyll, bundle 설치

```
 gem install jekyll bundler
 
 gem install webrick
```


- Jekyll 생성

```
 jekyll new ./
```

![Desktop View](/assets/img/2024-02-29/21.PNG)


해당 명령어를 실행할 때 다음과 같이 실행된다면 

```
jekyll new ./ --force
```

![Desktop View](/assets/img/2024-02-29/22.PNG)


다음과 같이 명령어를 작성하면 해결할 수 있습니다.

- bundle 설치

```
bundle install
```

- jekyll 서버 동작

```
 bundle exec jekyll serve
```

정상적으로 모두 실행 되었다면 주소창에 <http://127.0.0.1:4000/> 또는 <http://localhost:4000/>로 접속해서 화면에 **Hello! This is the first page!**가 나올 것입니다.

바뀐 테마로 보이지 않는 이유는 local에는 파일이 많아졌지만, Github Repository에는 어떠한 파일 변경을 하지 않았기 때문입니다. 따라서 local에 있는 여러가지 파일을 Github Repository로 전송해야 합니다.

Github Desktop을 열면 좌측에 local에 붙여넣었던 파일명이 뜨게됩니다. 

![Desktop View](/assets/img/2024-02-29/23.PNG)


Commit to main이라는 버튼을 눌러야되는데 활성화 되어있지 않습니다. 파일이 여러개이기 때문으로 내용을 직접 적은 후(아무 내용이나..)에 해당 버튼을 누른 뒤 Push origin 버튼을 눌러주면 됩니다.

-분 후에 본인의 Github Blog 주소에 들어가면 정상적으로 Page가 보이게 될 것입니다.


# 6.  오류 해결
---

하지만 전 **"--- layout: home # Index page ---"**라는 오류에 직면하게 되었습니다.


![Desktop View](/assets/img/2024-02-29/24.PNG)

![Desktop View](/assets/img/2024-02-29/25.PNG)


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


궁금하신 부분이나 괜찮으셨다면 댓글 부탁드려요💨
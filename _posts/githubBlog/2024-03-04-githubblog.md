---
layout: post
title: GitHub Blog 만들기 (2)
date:   2024-03-04 16:55:02 +09:00
categories: [GitHub Blog]
tags: [GitHub Blog]
---

## GitHub Blog 만들기 카테고리
---
[GitHub Blog 만들기 (1)](https://LeeNaYoung240.github.io/posts/2024-02-29-githubblog/)

[GitHub Blog 만들기 (2)](https://LeeNaYoung240.github.io/posts/2024-03-04-githubblog/)

[GitHub Blog 만들기 (3)](https://LeeNaYoung240.github.io/posts/2024-03-042-githubblog/)

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



![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/5204e8fa-ddf6-4c19-a709-b5969cc7519f)


상단의 사진과 같이 Owner/username.github.o를 선택하고 clone합니다.


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/c9fbd7d7-4cf0-4e07-8618-9f502f8163bf)


상단의 사진에서 Local path는 해당 경로의 폴더에 인터넷에 있는 Repository와 연동됩니다.


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/3432e5a5-88b4-4aa6-9431-601400f632c2)


좌측 상단이 정확히 진행되었는지 확인 하고 Open in Visual Studio Code 버튼을 누릅니다.


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/77ff3cc9-4a44-4ecf-aeec-7c06457710f0)


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


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/c6cc10b1-bc65-42d4-9756-ca5a44cf9faf)


그 후,  Github Descktop에 들어오면 다음과 같이 변경 되어있을 것입니다.


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/ce27157e-4ab7-4061-bdd9-cbe1be9cfddf)


좌측 하단의 Commit to main 버튼을 눌러줍니다. 


![image](https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/68fbf5c2-92dc-4d8c-9aab-2fed0620bc62)


그 후, Push origin 버튼을 눌러주면 됩니다.
Github 홈페이지의 username.github.io Repository에서 README.me 파일과 index.html 파일이 확인되면 Push가 완료된 것입니다. 
> https://username.github.io 를 접속했을 때 화면에 **Hello! This is the first Page!**라고 보인다면 완료입니다.
> 

# 5. 설치(Jekyll, Ruby)
---

Jekyll, Ruby 설치 전에 테마를 먼저 고릅니다. 다양한 Jekyll Themes를 지원하는 페이지가 있으니 원하시는 테마를 선택하시면 됩니다. 저는 <https://github.com/cotes2020/jekyll-theme-chirpy> 해당 github의 테마를 사용했습니다.


![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/b991a506-0828-4f00-a16d-bb850af7847b)


Code를 클린 한 뒤, Download Zip을 눌러 해당 압출폴더를 다운로드 합니다.



![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/4156ec13-afe2-42aa-af15-8efb5456c56d)


그 후, 본인의 Github Blog가 저장된 폴더에 


![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/ea05244e-8aec-492a-b51f-f8d4b2d4b6e4)

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/391eb666-f6ee-478a-9b34-b9d5e733577b)


다음과 같이 압축을 풀었습니다.  파일이 존재한다는 메시지가 뜬다면 덮어쓰기를 진행하면 됩니다.

다운 받은 파일을 수정하기 전에 Jekyll를 설치해야 됩니다. 다운 받은 파일은 Jekyll  기반으로 개발 되어있기 때문에 Jekyll을 설치하지 않을 경우 저희가 원하는 방식으로 테마를 수정할 수 없게 됩니다. Jekyll 테마를 설치하고 수정, 관리하기 위해서는 먼저 Ruby 개발 환경을 세팅해야 됩니다.


1)  Ruby 설치

Ruby를 설치하는 이유는 Jekyll이 Ruby로 만들어졌기 때문입니다.

><https://www.ruby-lang.org/en/downloads/>

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/fcb2ea39-6ac1-42d2-8d87-0ac19a1c2c7c)


전 Ruby+Devkit 3.2.2-1 (x64)을 다운로드 받았습니다.

설치 후에 윈도우 검색창에서 Start Command Prompt with Ruby를 실행합니다.



![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/9bec5f89-3857-4393-b9d6-f142f8f7e5d3)


그 후에 본인의 username.github.io이 저장된 경로로 이동해줍니다. 
위치를 모른다면 

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/942b54a0-880f-4f5d-a8d2-0da72089dcfd)

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

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/45e9afd0-2b1c-4572-a02a-95ea4e259e2b)


해당 명령어를 실행할 때 다음과 같이 실행된다면 

```
jekyll new ./ --force
```

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/5b4604b7-695b-469c-9479-e5d1141ebcea)


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

![image](https://github.com/LeeNaYoung240/Comment-Management/assets/107848521/e36a38df-ec2e-4cf8-b6a3-7b3f1bc54cb0)


Commit to main이라는 버튼을 눌러야되는데 활성화 되어있지 않습니다. 파일이 여러개이기 때문으로 내용을 직접 적은 후(아무 내용이나..)에 해당 버튼을 누른 뒤 Push origin 버튼을 눌러주면 됩니다.

-분 후에 본인의 Github Blog 주소에 들어가면 정상적으로 Page가 보이게 될 것입니다.

# 이어서
---
지금까지 Github Desktop과 VSCode, Jekyll, Ruby에 대해 설치했고 다음은 오류 해결 및 수정 작업에 대해 살펴보겠습니다.

궁금하신 부분이나 괜찮으셨다면 댓글 부탁드려요💨


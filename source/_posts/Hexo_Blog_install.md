---
title: "hexo_blog_install"
author: "gwiyoung"
date: '2022-03-18'
output: 
  html_document:
    keep_md: true
---


# Hexo Blog 만들기

참고 : [https://dschloe.github.io/settings/hexo_blog/](https://dschloe.github.io/settings/hexo_blog/)

1. 먼저 [nodejs.org](http://nodejs.org) 설치해준다

링크 : [https://nodejs.org/en/](https://nodejs.org/en/)  → 16.14.1 LTS 로 설치

![Untitled](/images/Hexo_Blog_install/Untitled.png)

1. 설치 완료 후 마우스 우클릭하여서 Git Bash Here 선택
    
    ![Untitled](/images/Hexo_Blog_install/Untitled%201.png)
    
2. 명령어 창이 뜨는데 거기서 아래 명령어를 입력하여 버전을 확인해준다
    
    ![Untitled](/images/Hexo_Blog_install/Untitled%202.png)
    

```bash
node -v
git --version
```

1. 확인이 되면 깃허브 홈페이지로 가서 New를 클릭하여 새로운 저장소를 만들어준다.

      (이름은 원하는대로 설정)

![Untitled](/images/Hexo_Blog_install/Untitled%203.png)

1. 설정 후 다시 2번의 상황을 반복한 후 아래의 명령어를 입력해준다.
    
    ![Untitled](/images/Hexo_Blog_install/Untitled%204.png)
    
    ```bash
    hexo init "폴더명"
    ```
    
2. 명령어를 입력해주면 바탕화면에 해당 폴더명으로 된 폴더가 생긴것을 확인.
3. 그 폴더에 마우스 우클릭하여 파이참으로 실행하기
    
    ![Untitled](/images/Hexo_Blog_install/Untitled%205.png)
    

1. 파이참에서 아래의 명령어를 입력하여 실행해준다

![Untitled](/images/Hexo_Blog_install/Untitled%206.png)

```bash
echo "# myblog" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/sungwiyoung/myblog.git
git push -u origin main
```

※ 주의할점은 본인이 만든 폴더명을 넣어주어야함

  - git add “내가 올리고자 하는 파일명”  // git add . → 해당 폴더에 있는 모든 파일

  - git commit -m “내가 넣고자 하는 메세지명”

  - git push 명령어를 입력해주면 업로드가 됨.

  - hexo server 를 입력하여 홈페이지가 잘 들어가는지 확인

1. 홈페이지 연동하기

  - 파이참을 실행하여 config.yml 더블클릭하여 진입

  - title, url, deploy를 변경해주어야함.

![Untitled](/images/Hexo_Blog_install/Untitled%207.png)

![Untitled](/images/Hexo_Blog_install/Untitled%208.png)

title : 원하는 타이틀로 입력해준다

url : `[https://sungwiyoung.github.io](https://sungwiyoung.github.io)` 자신의 사용자명이 들어가도록 바꿔준다

```
deploy:
  type: git
  repo: https://github.com/sungwiyoung/sungwiyoung.github.io.git
  branch: main
```

deploy에서도 repo 부분을 자신의 사용자명이 들어가도록 수정해준다.

1.  배포를 하기위한 준비

   - 아래의 명령어를 파이참에 입력해주어 패키지를 설치한다.

```bash
$ npm install
$ npm install hexo-server --save
$ npm install hexo-deployer-git --save
```

  - 4번과 동일하게 새로운 저장소를 만들어주는데 9번에서 입력한 url에서 사용자명에서 io까지로 입력하여 만들어준다.

![Untitled](/images/Hexo_Blog_install/Untitled%209.png)

  - 아래의 명령어를 입력해주어 배포를 해준다.

```bash
hexo generate
hexo deploy
또는
hexo generate deploy
```

  - 배포를 해준 후 다시 서버를 열어서 잘 들어가는지 확인해준다.

```bash
hexo server
```

1. hexo 홈페이지에서 나오는 첫번째 명령어를 입력해준다

  - hexo server 명령어 입력후 나오는 홈페이지에 있음

```bash
$ hexo new "My New Post"
```

![Untitled](/images/Hexo_Blog_install/Untitled%2010.png)

1. 입력해주면 파이참에  My-Nes-Post.md라는 파일이 생기는 것을 확인해준다.
    
    ![Untitled](/images/Hexo_Blog_install/Untitled%2011.png)
    

1.  테마설치(명령어만 입력해주면 자동으로 바뀜)

참고 페이지 : [https://hexo.io/themes/](https://hexo.io/themes/)

![Untitled](/images/Hexo_Blog_install/Untitled%2012.png)

  - 위 홈페이지 열린 후 파이참에서 아래의 명령어를 입력해준다

```bash
npm install -S hexo-theme-icarus
hexo config theme icarus
```

  - 위 명령어를 입력후 hexo server 명령어를 입력하여 테마가 잘 바뀌었는지 확인한다.

  - 오류가 날시에는 아래의 명령어를 입력해주어 다시 확인해준다.

```bash
npm install --save bulma-stylus@0.8.0 hexo-renderer-inferno@^0.1.3
```

  - 다시 서버를 열어보고 잘 되었는지 확인해준다.

![Untitled](/images/Hexo_Blog_install/Untitled%2013.png)

테마가 잘 바뀌었으면 정상적으로 된것임.

※ hexo clean 명령어로 청소해주기

★ myblog 저장소는 자료가 날라갈것을 대비한 백업용

★ ****[sungwiyoung.github.io](https://github.com/sungwiyoung/sungwiyoung.github.io) 저장소는 자동저장용**
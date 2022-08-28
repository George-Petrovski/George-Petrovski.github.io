---
title: Git & Github Basics
subtitle: Developer Tools
layout: post_detail
date-created: 2020-12-18
date-edited: 2021-06-26
img: dreams.png
thumbnail: 2020-12-18-git-github-basics-thumbnail.jpg
alt: image-alt
category: Post
description: Git & Github Basics
comments: true
---

### Git이란?
버전을 편리하게 관리할 수 있도록 도와주는 대중적이고 전문적인 도구  
e.g. 우리가 타임머신을 타고 원하는 순간으로 가고 싶은 것처럼, 우리가 작업하고 있는 파일들을 원하는 순간으로 다시 돌아갈 수 있게 만들어주는 도구

### 깃 사용방법
1. Terminal: Original Git - Command based program (Mac: iterm, Windows: cmder 추천!)
2. GUI Application
* Source Tree: 대중적인 도구
* Github desktop: 기능 많이 없음
* Git kraken: 멋진 UI

### 깃 기본 명령어 (Windows Terminal)
1. git -- version: 깃 버전확인
2. git config -- list: 깃 설정 확인

### 초기설정
1. .gitconfig 파일: 모든 환경설정
* git config -- global core.editor “code [--wait]”: Text Editor로 연결해서 Git을 사용하는것도 가능
2. git config --global user.name “username”
3. git config --global user.email “email@example.com” 
4. git config --global core.autocrlf true
* Text editor에서 Windows에서는 text \r\n (line feed) 동시에 들어감, Mac에서는 text\n (line feed) 만 들어감. (\r = carriage return)
* 다양한 운영체제에서 git 사용시 git history에 보는데 문제가 생길 수 있음
* 맥도 따로 처리 해주는 이유는 이메일에서 내용 복사해올 시에 \r이 자동으로 들어갈 수도 있음

### 깃 초기화/삭제하기
1. mkdir git
2. git init: git project 시작
3. rm -rf .git: git project 삭제
4. git status: git status check
5. git config --global alias.”shorthand” “command”: shorthand type command configuration
6. git config --h: command helper

### Git working flow (file status)
1. Working directory: file modifying, working space
* Untracked
* Tracked: Tracked by version history(commit)
  * Unmodified: 
  * Modified: Allow to ‘add’ to staging area
2. Staging area: files get ready to commit version history
3. .git directory: git version history record
* Local repository: My computer
* Remote repository: github server
4. Tip. Commit components
* Name, date, time, file…

### git add
1. How to commit
* git add “filename.type”: add to staging area
* Untracked files or tracked&modified files
2. How to remove commit(or add)
* git rm --cashed “filename”
3. E.g. If a.txt has been added to staging area with git add * and deleted in working area. the result of git status is including a.txt. However, if we use git add . after the file is deleted, the deleted file is removed from the staging area.

### git ignore: tracking 하고 싶지 않은 파일(e.g. log)
1. .gitignore 숨겨진 파일 생성 후 텍스트 파일에 commit하고 싶지않은 파일들 제목을 올린다.
* echo *.log > .gitignore => add 가능한 목록에서 사라짐
* gitignore 파일안에 특정 디렉토리 or 특정 format을 가진 파일들을 넣어서 제외시킬 수 있음. 

### git status: 작업사항 간단히 확인
1. git status --long:
2. git status --s: A (add), ??: working directory untracked
3. git status --[option]: 

### git diff: working directory에서 변경사항
1. command cat command: 파일 내용 확인
2. git diff --staged(or --cached): 
3. git difftool: tool을 이용하여 git diff 조회 (git config --global -e를 통해 editor를 설정후 사용 가능)

### First commit
1. 구성
* Title
* Description
2. Git log:git log 확인
3. Git add . 후 git commit 후 vscode 이용하여 Title, description 추가 후 닫으면 자동으로 commit
4. 파일 수정 후 git add . 후 git commit -m “commit name” 입력하면 따로 vscode 실행하지 않고 바로 commit 가능 (-m [message option])

### Git commit 팁
1. 규모?
* History에는 작은 단위로 나눠서 저장하는게 좋음
* 현재, 동사원형으로
* 각 commit에 해당되는 내용만 포함할 것
2. E.g. initialize project, add loginservice module, => 의미있는 청크 덩어리로 작업한 내용 commit할 것

---

### Source
[2020-11-17 깃, 깃허브 제대로 배우기 - 드림코딩 by 엘리](https://www.youtube.com/watch?v=Z9dvM7qgN9s){:target="_blank"}
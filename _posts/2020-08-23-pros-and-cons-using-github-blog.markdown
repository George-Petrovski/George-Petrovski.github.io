---
title: Pros & Cons of Blog
subtitle: Website Design
layout: post_detail
date-created: 2020-08-23
date-edited: 2021-06-07
img: dreams.png
thumbnail: 2020-08-23-pros-and-cons-using-github-blog-thumbnail.jpg
alt: image-alt
category: Post
description: Pros & Cons of using Github Blog
---

# Pros & Cons of using Github Blog

---

### 목차

* 블로그 만들기 GitHub 총정리
* [블로그 만들기 GitHub 기본 1편 - 사용자 페이지](https://blog.chulgil.me/how-to-make-blog-using-github-1/)
* [블로그 만들기 GitHub 기본 2편 - 프로젝트 페이지](https://blog.chulgil.me/how-to-make-blog-using-github-2/)
* [블로그 만들기 GitHub 심화 3편 - 커스텀 도메인](https://blog.chulgil.me/how-to-make-blog-using-github-3/)
* [블로그 만들기 GitHub 심화 4편 - Jekyll 템플릿](https://blog.chulgil.me/how-to-make-blog-using-github-4/)
* [블로그 만들기 GitHub 심화 5편 - GitBook만들기](https://blog.chulgil.me/how-to-make-blog-using-github-5/)


---


### 이 글에서는 왜 [GitHub Pages](https://help.github.com/articles/what-is-github-pages/)를 사용하면 어떤점이 좋은지, 활용하는 방법은 어떤것들이 있는지를 공유한다.
GitHub Pages는 GitHub저장소의 내용을 호스팅해주기 때문에 및 웹서버 설치없이 공짜로 블로그를 쉽게 만들수 있다.
원래 Git은 소스코드의 변경사항을 관리해주는 툴인데 온라인으로 소스코드를 관리할 수 있게 서비스해주는 곳이 GitHub이다.

최근 나를 포함한 많은 개발자들이 정적 사이트로 블로그를 발행하고 있다.

---

### 그 이유는 다음과 같이 추려볼 수 있다.

1.  블로그를 운영하다가 트래픽 증가로 인한 서버관리를 지속하기가 힘들다.

2. SQL injection같은 보안이슈를 생각하고 싶지 않다.

3. 호스팅업체에 매월 나가는 돈이 아깝다.

4. 효율적인 SEO를 위해서는 웹사이트의 스피드가 중요한데 속도 또한 빠르다.

5. Markdown 을 이용해서 디자인에 신경쓰지 않고 글쓰기에 집중할 수 있다.

6. HTML로 만들어진 문서를 배포하기 쉽다.(아마존S3, 저비용호스팅, 개인서버)

7. Jekyll을 Github CEO가 만들었기 때문에 github에서는 이미 지원하고 있다.

8. Visual Code와 같은 개발툴로도 작성할수 있기때문에 회사에서도 눈치보지 않고 포스팅이 가능하다.

9. [kakao기술 블로그](http://tech.kakao.com/2016/07/07/tech-blog-story/)와 같이 대기업들도 활용하고 있는 곳이 많다.

10. 백엔드 서버언어를 사용하지 않고 정적파일들로 호스팅을 제공 하기때문에 html, css, javascript를 이용해서 쉽게 웹사이트를 만들고 도메인까지 붙일 수있다.

11. Git와 같은 버전관리 프로그램을 통한 편집이력 관리도 용이하다.


---

확실히 개인 블로그로만 활용한다고 하면 이렇게 효율성 좋은 서비스는 찾아보기 어렵다.
글을 작성하는 사람이 본인이기 때문에 로그인인증도 필요없고 내가 글을 작성하는 시점에 웹에 보여지기만 하면 되는 것이기때문에 동적인 플랫폼을 사용하는 것보다 본래의 HTML을 제공한다면 관리하기도 쉽다. 게다가 루비기반으로 만들어진 Jekyll과 같은 사이트생성기를 사용하면 Header와 Footer같이 반복되는 페이지들도 split할수가 있다.


---



### 사용하기 꺼려하는 이유

이런 장점에도 불구하고 사용하기 꺼려하는 이유가 있는데 다음과 같다.

1. Markdown을 공부하기 귀찮다.

2. 사이트 구조의 개선이 어렵다.

3. 댓글기능이 제공되지 않아 써드파티 서비스를(Disqus) 이용 해야만한다.

4. 상기 댓글과 같은 사용자 데이터를 확보하기 힘들다.

5. 검색기능 구현이 까다롭다.

6. 너무 개발자 스럽다.


---


블로그에 글을 쓸경우 보통의 동적플랫폼은 Admin패널에 가서 글쓰기를 하면된다지만
정적 블로그 생성기를 사용하는 경우는 일반인 입장에서는 까다롭다.
Admin패널처럼 이용하려면

1. github에 가서 파일을 생성하고 commit을 하거나

2. 본인의 컴퓨터에서 문서를 작성하고 git push를 하는것과 같다.

---

### 결론

개인적으로 활용해본 결과 동적 플랫폼으로 만들어 놓은 사이트는 구축및 운영에서 힘들었는데

Github Pages와 같은 정적사이트호스팅을 이용하면 설치도 쉬웠고 글을 올리는과정을 제외하고는

웹사이트 관리 및 운영이슈는 딱히 없어서 편했기 때문에 블로그를 시작하시는 분들에게 적극 추천드린다.

---

### Reference

블로그 만들기 GitHub 편 총정리
(https://blog.chulgil.me/how-to-make-blog-using-github/) - Chulgil.Lee
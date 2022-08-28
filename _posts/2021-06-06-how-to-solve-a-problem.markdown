---
title: How to solve a problem
subtitle: Problem Solving Procedure
layout: post_detail
date-created: 2021-06-06
date-edited: 
thumbnail: 2021-06-06-how-to-solve-a-problem-thumbnail.jpg
alt: image-alt
category: [Post, Skills]
description: Improving Problem Solving Skill
comments: true
---

문제인식 2021-06-06
현상: responsive 오류
mobile 환경(width: 360px)에서 nav menu와 full width가 안맞는 현상 발생 => 그로인해 contents 살짝 오른쪽에 여백이 생김
=> 기존 agency theme에서는 문제없이 작동


고장탐구1: style.css 훑어보기 => 뭔가 nav margin-right에 영향을 끼쳤나?
고장탐구 결과:이상없음... nav class 자체에 margin right 및 github에서 agency.css를 많이 바꾼적 없음...

고장탐구2: github 이용해서 언제부터 그랬는지 추적 (캡처)
=> Update portfolio_grid.html and post_grid.html
=> Docker로 실시간으로 local 업데이트

문제점: portfolio_grid.html에 Tell me more 버튼을 추가하면서 생긴 오류 어쩌다가 nav menu에 영향을 끼쳤는지...


Stack: Docker, Jekyll, Github, Git
Command: git reset --hard <commit_id>
---
title: Move Git repository
subtitle: Move a Git repository
layout: post_detail
date-created: 2020-08-27
date-edited:
img: dreams.png
thumbnail: 2020-08-27-move-git-repository-thumbnail.jpg
alt: image-alt
category: Post
description: How to move a full Git repository with Commit history
comments: true
---

# 내 저장소에 있는 모든 파일들을 통째로 다른 repository로 옮기고 싶을 때! - Github

---



아직 Git을 잘 모르는 상태인데( 특히 branch..) BoostCamp Git이 만들어졌어요. 

이제 내 개인의 저장소가 아닌, 이 곳에서 add, commit, push 작업을 진행하게 될 것 같아요 . 

"하지만 나는 내 저장소에만 저장해놨는데...이걸 그대로 commit이력까지 복사해서 통째로 다른 저장소로 옮길 방법이 없을까?"라는 궁금증이 들었어요!

Git초보자 에게는 어려울수도 있으니 ( 처음에 저한테는 너무 어려웠어요 ㅠㅠ )방법을 공유해보려고 해요: )

잘 따라하면 쉬우니 다들 따라해보세요! 



---



먼저 **옮기고 싶은** (지금은 제 저장소) **저장소 https 주소**를 복사주세요!! 

제 저장소 https주소를 보는법은 git에서도 볼 수 있지만 터미널로도 볼 수 있어요. 

현재 내가 연결되어있는 Git을 보려면 git remote 를 터미널창에 입력해주세요.

자세히 보고싶으시다면 `git remote -v`를 입력해주세요.

![img]({{ site.url }}{{ site.baseurl }}/assets/images/post/2020/08/27/2020-08-27-how-to-move-a-full-git-repository-with-commit-history/01. Type git remote -v.png){: .align-center}

여기가 제 저장소 랍니다. :)

원하시는 방법으로 현재 제 저장소의 https주소를 복사했다면, 밑의 커맨드라인에서 주소부분만 바꾸어 터미널창에 입력해주세요. 

​	`git clone --mirror https://example.git`



![img]({{ site.url }}{{ site.baseurl }}/assets/images/post/2020/08/27/2020-08-27-how-to-move-a-full-git-repository-with-commit-history/02. Type git clone --mirror.png){: .align-center}

이렇게요!! 



---



그리고 다시 remote를 하여 '길'을 만들어주는 작업을 할 겁니다.

이제 저는 제 저장소가 아닌 다른 저장소에서 작업을 한다고 그랬죠?

그러면 제가 소스코드를 수정하고 다시 add, commit, push했을 때, 제 저장소가 아닌 새로운 저장소에 작업이 수행되어야 겠죠??

그러면 우리는 **제 로컬Git**과 **새 repository**를 **연결**해주는 '길'을 만들어야해요. 그럴려면 제가 올릴 소스코드 들이 있는 곳으로 이동해야겠죠? 저는 아예 처음부터 제 제가 올릴 소스코드가 있는 곳에서 작업을 했답니다. 아닌 분들은 cd명령어를 통해 디렉토리를 꼭 이동해주세요!!!

그리고 우리가 옮길 **새로운 저장소의 https주소**를 복사해주고, 

`git remote set-url --push origin https://example`을 터미널창에 입력해주세요

![img]({{ site.url }}{{ site.baseurl }}/assets/images/post/2020/08/27/2020-08-27-how-to-move-a-full-git-repository-with-commit-history/03. Type git remote set-url --push origin.png){: .align-center}

이렇게요 :) 이제 '길'이 만들어진거랍니다XD



---



이제 마지막으로 push를 해야겠죠? 

`git push --mirror`를 터미널창에 입력해주세요.

![img]({{ site.url }}{{ site.baseurl }}/assets/images/post/2020/08/27/2020-08-27-how-to-move-a-full-git-repository-with-commit-history/04. Type git push --mirror.png){: .align-center}

이러면 제 원래 저장소에 있던 모든 파일과 commit이력까지 새로운 저장소로 옮겨지게 된답니다 XD 

Git은 간편하면서도 어려운 것 같아요. 저도 아직 Git 초보라 배워야 할게 정말 많은 것 같아요.

이제 길이 새로운 곳으로 잘 만들어졌나 확인해 볼까요?  위에서 처럼 remote명령어를 통해 확인해 볼게요.

![img]({{ site.url }}{{ site.baseurl }}/assets/images/post/2020/08/27/2020-08-27-how-to-move-a-full-git-repository-with-commit-history/05. Type git remote.png){: .align-center}

새로운 저장소로 바뀐 게 보이시나요? ㅎㅎ

잘 따라하시고 도움이 되었으면 좋겠어요 :)



ps. 제목을 쓰다가 헷갈려서 찾아본건데 통채로가 아니라 통째로가 맞는 표현이네요 :) 통채로는 통째로의 비표준어라 하니 주의해서 써야겠어요.



---



## Sources

* https://zeddios.tistory.com/5
* https://stackoverflow.com/questions/17371150/moving-git-repository-content-to-another-repository-preserving-history
* https://www.atlassian.com/git/tutorials/git-move-repository
* https://itnext.io/git-repository-transfer-keeping-all-history-670fe04cd5e4
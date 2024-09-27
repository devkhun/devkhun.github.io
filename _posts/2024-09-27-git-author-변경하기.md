---
title: "Git author 변경하기"
categories: [Junk, Git]
tags: [Git]
toc: true
toc_sticky: true
---

# Git author 변경하기
* 만약 git log의 3번째 커밋의 author를 변경하고 싶은 경우 ?

```
$ git rebase -i HEAD~3 # 3번째 커밋을 변경하고자함

# vi 화면이 뜨면
# pick -> e 로 변경하고 :wq로 저장 & 종료

$ git commit --amend --author="{username} <{useremail}>"

# 또 vi 화면이 뜸
# 이때 변경 된 author 내용 확인 후 :wq 

$ git rebase --conitnue 
$ git push -f origin main
```

* 후,, 현재 다니는 회사가 이런거에 너무 빡빡해서 너무 스트레스 !

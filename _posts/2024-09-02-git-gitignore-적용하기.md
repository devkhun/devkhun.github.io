---
title: "Git .gitignore 적용하기"
categories:
  - git_basic
tags:
  - git
---

### Git .gitignore 적용하기
* `root` 디렉토리에 `.gitignore` 파일 생성 후 형상관리가 되면 안되는 파일들 기입

```
# git cache 삭제
$ git rm -r --cached .
$ git add .
$ git commit -m "cache clear"
```

* 또는 아래와 같이 git 추적금지를 시킬 수 있음

```
git update-index --assume-unchanged
git update-index --no-assume-unchanged

git rm --cached filename
git rm --cached .htaccess

git rm -r --cached .
git add .htaccess
git commit -m 'clear git cache'
```

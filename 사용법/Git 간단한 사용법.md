# Git

> Git은 분산 버전 관리 시스템(DVCS)이다. Distributed Version Control System
>
> 소스코드의 버전 및 관리 이력을 관리할 수 있다.



## 준비하기

윈도우에서 git을 활용하기 위해서는 [git bash](https://git-scm.com/)를 설치한다. 

git을 활용하기 위해서 GUI 툴인 `Source Tree`,`Github Desktop`등을 활용할 수 있다.

초기 설치를 완료한 이후에 컴퓨터에 `author` 정보를 입력한다.

- `$`은 shell 명령어를 의미하며, 실제로 입력하지 않는다.

```shell
$ git config --global user.email "dng20@naver.com"
$ git config --global user.name "leejunhyeokk"
```

- 설정 확인하기

```shell
$ git config --global user.email
$ git config --global user.name
```



## 로컬 저장소(repository) 활용하기

### 1. 저장소 초기화

```-g-
$ git init
```

- `.git`폴더가 생성되며 여기에 git과 관련된 모든 정보가 저장된다.
- git bash에 `(master)`라고 표시되는데, 이는 현재 `master` brach에 있다는 뜻이다.



### 2. add

`working directory`(작업 공간)에서 변경된 사항을 이력으로 저장(commit)하기 위해서는 반드시 `staging area`를 거쳐야한다.

```shell
# 특정 파일
$ git add 변경한 파일 이름
$ git add Git.md
# 특정 폴더
$ git add 변경한 폴더 이름
$ git add images/
# 현재 디렉토리를 기준으로 하위 모든 변경 사항
$ git add .
```

- add 전 상태

```shell
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Git.md

no changes added to commit (use "git add" and/or "git commit -a")
```

- add 후 상태

```shell
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   Git.md
```



### 3.commit

이력을 확정짓는 명령어로, 해당 시점의 스냅샷을 기록한다.

커밋시에는 반드시 메시지를 작성해야하며, 메시지는 변경사항을 알 수 있도록 명확하게 작성(영어-명령문)한다.

```shell
$ git commit -m "마크다운 정리"
[master bead27a] 마크다운 정리
 1 file changed, 90 insertions(+)

```

커밋 이후에는 아래의 명령어를 통해 지금까지 작성된 이력을 확인한다.

```shell
$ git log
commit bead27a5859a99cece524b949c09af0029b06e9b (HEAD -> master)
Author: leejunhyeokk <dng20@naver.com>
Date:   Fri Jul 17 11:49:42 2020 +0900

    마크다운 정리

commit 253ce1504552cc9ba67e7d98785e106b909a64c6 (origin/master, origin/HEAD)
Author: leejunhyeokk <dng20@naver.com>
Date:   Fri Jul 17 11:20:53 2020 +0900

    Add markdown file

commit 637deb4b28ee40e9af94f4fec5a0702f32e4d376
Author: leejunhyeokk <dng20@naver.com>
Date:   Thu Jul 16 17:39:56 2020 +0900

    First commit
```

커밋은 해시값을 바탕으로 구분된다.



### 원격 저장소(remote repository) 활용하기

> 원격 저장소 기능을 제공하는 다양한 서비스 중에서 github를 기준으로 설명한다.

#### 0. 준비사항

- github 계정 및 repository

#### 1. 원격 저장소 등록

```shell
$ git remote add origin https://github.com/leejunhyeokk/til.git
```

- 원격 저장소`(remote)`로 ,origin이라는 이름으로, `github url`을 등록`(add)`한다.
- 등록된 원격 저장소 목록을 보기 위해서는 아래의 명령어를 입력한다.

```shell
$ git remote -v
origin  https://github.com/leejunhyeokk/til.git (fetch)
origin  https://github.com/leejunhyeokk/til.git (push)
```



#### 2. 원격 저장소 업로드(push)

```shell
$ git push origin master
```

`origin`으로 설정된 원격 저장소에 `master` 브랜치를 업로드(push) 한다.

이후 변경사항이 생길 때 마다. `add` - `commit` - `push` 를 반복하면 된다.

그리고, 항상 모든 명령어 이후에 연관된 상태(`status`,`log`,`remote -v`)를 확인하자.



#### 3. 원격 저장소 내용 반영하기 (pull)

```shell
$ git pull origin master	
```


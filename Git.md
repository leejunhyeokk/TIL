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
# Github

How to use Git and Github

# 1. Git이란 무엇인가?

#### Git - 파일에서 만든 변경사항을 추적하는 시스템

#### 워드, 이미지, 포토샵, 소스코드 등등 모든 형태의 파일들의 변경사항을 포함.

=> 언제 무엇을 변경했는지 알 수 있다. 팀으로 일하는 경우 누가 무엇을 언제 변경했는지 파악 가능

# 2. Git을 확인할 수 있는 곳은 어디인가?

#### 1) 내 컴퓨터에서 확인 가능

=> 만약 내 컴퓨터를 잃어버린다면? -> 걍 망하는 것.....

#### 2) 따라서 Distributed Version Control이 존재!! (Github)

Push 해서 올림 => 모든 변경사항과 내용들이 클라우드 서버에 저장됨.

# 3. Version Control

#### 1) Repository

소스코드를 저장하는 폴더, 변경이 일어났다면 Git이 그것을 추적.

#### 2) Commit

파일 변경 기록함 => 예를들어, 채팅창을 만들고 이에 대해 '채팅창을 만들었음' 이라고 기록하는 것을 Commit이라고 함.

#### 3) Branch

Master Branch => 디폴트로 생성됨. 모든 Commit이 반영된다.

ex) master branch가 마지막 결과물이고 많은 사람들이 이 코드를 사용하고 있다고 가정.

=> **이런 상황에서 새로운 기능을 추가하고 master branch는 건들고 싶지 않다!! 이럴때 새로운 branch를 가지처럼 만든다 !!**

#### 4) Branch 활용 과정

<u>(1) 브랜치를 만들고</u>

<u>(2) 마스터는 건들지 않고</u>

<u>(3) 브랜치에서 작업이 완료되면</u>

<u>(4) 브랜치를 마스터에 결합시킨다.</u>

# 4. Git vs Github

### Git은 코드의 변경사항을 추적하는 시스템

=> 코드가 언제, 어떻게, 누구에 의해서 변경 되었나 기록하는 것.

### Github는 이런 변경사항을 클라우드에 기록하는 웹사이트

=> 인터넷 저장소, Git을 업로드하고 관리하는 플랫폼.

# 5. Github Desktop

### Git을 활용하는 방법은 2가지가 존재.

#### 1) 콘솔을 활용

초보자에게 비추천. 하지만 빠르다.

#### 2) Github Desktop

Github에서 만든 소프트웨어. 작성한 코드를 비쥬얼하게 보여줌.

# 6. Github 명령어

### git add

`git add`는 파일의 변경사항을 Staging Area에 올리는 것을 말한다. 만일 index.html 파일을 변경했다면 `git add index.html` 이라 콘솔에 입력한다. 만일 파일을 삭제한 것을 add 하고 싶다면 `git add -u` 작성해 업데이트를 한다.

### git status

`git status` 는 현재 수정된 사항이 어떤 것이 있는지 알려주는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

### git diff

`git diff` 는 코드 줄 별로 변경사항을 알려주는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git diff
diff --git a/index.html b/index.html
index 4e47f2d..a641680 100644
--- a/index.html
+++ b/index.html
@@ -25,6 +25,7 @@
       <li>정재규</li>
       <li>공효은</li>
       <li>최영진</li>
+      <li>김선재</li>
     </ol>
     <h2>프로젝트</h2>
     <p>1. 블록체인을 이용한 신분조회 서비스</p>
```

### git commit 

`git commit` 명령어는 commit 영역에 코드를 올리는 작업이다. `git add` 를 하고 그에 해당하는 작업을 commit 영역에 올려준다. `git commit -m "메세지"` 메세지 안에 개발자가 메모하고 싶은 내용을 담아서 commit할 수 있다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git commit -m "Change member"
[master c26d383] Change member
 1 file changed, 1 insertion(+), 1 deletion(-)
```

### git log

`git log` 명령어는 해당 저장소에서 발생한 모든 commit을 보여준다. `git log --oneline` 명령어는 `git log` 명령어가 자세한 사항을 보여주기 때문에 간결하게 보고 싶을 때 사용하는 명령어이다. `git log --oneline --graph` 명령어는 좀 더 시각적으로 commit들에 상관관계를 보여주는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git log --oneline
c769721 (HEAD -> master) Bye~
ef68b6e add contents to project
241669c start project list
448c3d3 add team member list
2e499e3 add skillsets
e17f1d7 First Commit
```

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git log --oneline --graph
*   a59662d (HEAD -> master) Merge branch 'side'
|\
| * abe1ab8 (side) 2. JavaScript Project
* | c769721 Bye~
|/
* ef68b6e add contents to project
* 241669c start project list
* 448c3d3 add team member list
* 2e499e3 add skillsets
* e17f1d7 First Commit
```

### git branch

`git branch` 명령어는 현재 git 폴더에 해당하는 branch를 모두 보여준다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git branch
* master
  member
```

`git branch [name]` 명령어는 새로운 branch를 하나 생성한다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Programming/github (master)
$ git branch hi
```

`git branch -d [name]` 명령어는 입력한 이름에 해당하는 branch를 삭제한다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Programming/github (master)
$ git branch -d hi
Deleted branch hi (was c26ddec).
```

### git checkout

`git checkout [name]` 명령어는 입력한 이름에 해당하는 branch로 `HEAD`를 옮긴다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (pages)
$ git checkout master
Switched to branch 'master'
```

`git checkout -b [name]` 명령어는 입력한 이름으로 branch를 생성하고 해당 branch로 `HEAD` 를 옮긴다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git checkout -b member
Switched to a new branch 'member'
```

### git remote

`git remote` 명령어는 해당 로컬 저장소를 원격저장소와 연결시키는 명령어이다.

`git remote add [name1][name2]` 명령어는 name1이라는 가상 저장소를 name2 라는 원격저장소에 연결하는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (pages)
$ git remote add root https://github.com/parkchoongho/branching.git
```

`git remote -v` 명령어는 해당 로컬 저장소가 어떤 원격저장소와 연결되어 있는지를 알려주는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (pages)
$ git remote -v
root    https://github.com/parkchoongho/branching.git (fetch)
root    https://github.com/parkchoongho/branching.git (push)
```

### git push

`git push [name1] [name2]` 명령어는 name1 가상 저장소의 name2 branch에 commit한 내용들을 연결되어 있는 원격 저장소에 밀어넣겠다는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (pages)
$ git push -u root pages
Enumerating objects: 49, done.
Counting objects: 100% (49/49), done.
Delta compression using up to 2 threads
Compressing objects: 100% (33/33), done.
Writing objects: 100% (49/49), 4.39 KiB | 73.00 KiB/s, done.
Total 49 (delta 20), reused 0 (delta 0)
remote: Resolving deltas: 100% (20/20), done.
To https://github.com/parkchoongho/branching.git
 * [new branch]      pages -> pages
Branch 'pages' set up to track remote branch 'pages' from 'root'.
```

처음으로 `git push` 명령어를 사용할 때는 `git push -u [name1] [name2]` 라고 작성한다.

### git pull

`git pull [name1] [name2]` 명령어는 이미 연결되어 있는 원격 저장소에서 변경 사항을 가져올 때 사용하는 명령어이다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git pull root master
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/parkchoongho/branching
 * branch            master     -> FETCH_HEAD
   aad3887..9916bab  master     -> root/master
Updating aad3887..9916bab
Fast-forward
 index.html | 1 +
 1 file changed, 1 insertion(+)
```

### git clone

`git clone` 명령어는 원격 저장소를 로컬 저장소로 가져오고 싶을 때 사용한다.

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Programming
$ git clone https://github.com/parkchoongho/github.git
Cloning into 'github'...
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 8 (delta 1), reused 7 (delta 0), pack-reused 0
Unpacking objects: 100% (8/8), done.
```

### git merge

`git merge [name]` 명령어는 name branch를 지금 있는 branch와 합할 때 쓰는 명령어이다. (master branch에서 사용합니다.)

```bash
user@DESKTOP-P2A3NBM MINGW64 ~/Desktop/Project/codes/branch (master)
$ git merge side
Auto-merging index.html
Merge made by the 'recursive' strategy.
 index.html | 1 +
 1 file changed, 1 insertion(+)
```

 
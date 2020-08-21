# git?

## git의 목적
  1. collaborate
  2. version 관리
  3. backup
<hr/>

## terminology
  
  1. working tree - 파일을 수정하는 공간
  2. staging area - 버전을 만들려고 하는 파일들
  3. repository - 만들어진 버전
  
  즉, 
  working tree에서 버전관리를 하고 싶으면 staging area에 버전을 올리고 
  이것을 버전으로 만들려면 staging area의 파일들을 버전으로 만들고, 
  repository에 올리는 일련의 작업의 연속이 git이다.
<hr/>

## 주요 명령

* `add`
  + local repository의 파일들을 git이 tracking하도록 staging area에 올려 놓는 명령
* `commit`
  + 응용프로그램의 version 관리에 사용되는 명령, remote repository로 가기 위한 최후의 단계
* `push`
  + status working tree에 올라와 있고, commit이 된 파일들을 remote repository에 업로드 시키는 명령
* `pull`
  + remote repository에 있는 내용과 local repository에 있는 내용은 같아야 하므로, 윈격 -> 로컬 방향으로 동기화 시키는 명령
  + fetch + merge가 합쳐진 명령
* `checkout`
  + branch를 변경하거나, 현재commit을 이전 commit으로 되돌리기 위한 명령어
* `branch`
  + 하나의 부모 local repository(관습적으로 이름이 master)에서 파생되어 여러개의 branch 생성이 가능
  + 객체지향 프로그래밍이론 중, 상속.. 하나의 조상 클래스를 상속하는 여러개의 자식클래스와 비슷한 개념임
* `remote`
  + remote는 local과 remote repository를 짝 지어주기 위한 명령이라고 생각하면 이해하기 쉽다.
  + remote 명령으로 현재 서로 연결된 remote repository를 추가/삭제/변경 가능
* `clone`
  + remote repository의 내용을 그대로 local repository로 가져오는 명령
* `log`
  + 프로그램의 버전(commit)들을 볼 수 있는 명령
* `status`
  + staging area에 있는 파일들을 볼 수 있는 명령
<hr/>

## 명령 예시
```shell
$ git pull
$ git add <staging area에 올릴 파일 . 하면 다 올라감>
$ git status
$ git commit -m "v1.0"
$ git log
$ git push

$ git branch <branch_name>
$ git checkout <branch_name>
$ git checkout <commit_id>

$ git remote add origin <remote repository http address>
$ git remote remove origin

$ git clone <remote repository http address> <optinal--> <local repository name>
```
<hr/>

## Maintain Submodule

+ directory structure
```
Parent_dir
|
|--submodule1
...
```
+ update submodule
```
$ cd submodule

work ...

$ sh git.sh # use my script

$ cd ..

$ git add .

$ git commit -m "submodule change"

$ git push
```
**즉, 서브모듈에서 작업한 내용을 푸쉬하면 서브모듈의 origin으로 반영되고,**   
**부모 레포지토리에서는 반영 이전의 상태이기때문에 부모 레포지토리도 푸쉬해야한다.**
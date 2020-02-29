# git

## 주요 명령

* `add`
  + local repository의 파일들을 git이 tracking하도록 status working tree에 올려 놓는 명령
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


## 명령 예시
```shell
$ git pull
$ git add .
$ git commit -m "v1.0"
$ git push

$ git branch <branch_name>
$ git checkout <branch_name>
$ git checkout <commit_unique_number>

$ git remote add origin <remote repository http address>
$ git remote remove origin

$ git clone <remote repository http address> <optinal--> <local repository name>
```

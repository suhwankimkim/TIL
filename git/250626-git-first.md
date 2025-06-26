# Git!!!!!!!!!

## 머리말
- 오늘 Git에 대한 전반적인 내용을 배움 git이 무엇인지 왜 쓰는지 github는 뭔지 commit, branch 등등 다양한 개념을 배웠고 연습해보았다.

## Git이란?
- 분산형 버전관리 시스템(Git: distributed Version Control System)으로 Linus Torvalds라는 사람이 Linux 커널 관리를 위해 라이센스관련 분쟁이 발생하자 화가나서 1주일만에 만들어버린 미친사람이 만든 미친 업계 부동의 1위 자리를 갖고 있는 system

### Git의 특징
1. 단순한 구조와 빠른 속도
2. 분산형 저장소 지원
3. 비선형적 개발(수천개의 브랜치를 생성) 가능

### Git의 장점
1. 소스코드 주고받기 없이 동시작업이 가능해져 생산성 증가
2. 수정내용 commit단위로 관리, 배포 뿐 아니라 원하는 시점으로 돌아갈수도 있음
3. 새로운 기능 추가는 Branch로 공간을 확장하여 도전적으로 실험이 가능하고 성공적으로 개발이 완료되면 병합도 가능 엄청 도전적으로 실험 할 수 있음
4. 인터넷이 연결되어 있지 않아도 개발할 수 있음
* 발표자료.pptx, 발표자료_최종본.pptx, 발표자료_최종최종본.pptx와 같은 대참사 방지

## CLI? GUI?
* CLI는 command line interface, GUI는 Graphic User Interface로 우리가 흔히 window에서 그림으로 이루어진 아이콘을 클릭해서 직관적으로 무언가를 실행하는 것을 GUI, 지금 작성하고 있는 vim이나 cmd같은 곳에서 한줄 씩 명령어를 입력해서 사용하는 것을 CLI라고 한다. 
* 일전에 aws를 사용할 때도 그렇고 지금 git을 사용할 때도 맞찬가지고 cloud platform관련작업을 위해서는 cli가 필수적이므로 훈련이 필요하고 익숙해지면 gui보다 cli가 편하다고는 하는데 잘 모르겠음
* gui와 cli의 가장 큰 차이점은 파일을 실행할 때 gui는 연결된 프로그램을 통해 파일이 열리지만 cli는 어떤한 도구로 열지를 다 지정을 해주어야 한다. 예를 들어 python 파일을 열때 python test.py와 같은 명령어로 실행을 해야한다.

## Shell
* 운영체제의 커널과 사용자를 이어주는 소프트웨어 즉 컴퓨터와 인간사이에 대화를 할 수 있게 도와주는 번역기라고 생각하면 된다. 다양한 SHELL이 있고 윈도우에서는 주로 git bash, mac에서는 zsh를 사용한다.

## Shell command
** 주요한 shell command 몇개를 소개**
- cd : change directory에 줄임말로 작업경로를 설정 해줄 때 사용한다.
    - cd 경로 : 경로로 이동
    - cd .. : 상위 경로로 이동
    - cd : 최상위 경로로 이동
- ls : 현재 작업경로에 존재하는 모든 directory, file을 표기해준다.
    - ls -l : 더 자세하게 확인하고 싶을 때 옵션
    - ls -a 숨긴파일까지 모두 보고 싶을 때 사용 
    - ls -al or ls -a -l과 같이 쓸 수 있음
- pwd : 현재 작업경로 표기
- mkdir [파일 name] : 파일을 만드는 명령어 파일이름 앞에 경로를 적어 놓으면 경로상에 파일이름에 해당하는 파일을 만들어줌
- touch [파일 name] : mkdir과 같은 역할을 함
- mv [파일이름1] [파일이름2] : 파일이름1을 파일이름2로 변경
    - mv [파일이름1] [경로/파일이름1] : 파일이름1을 경로상으로 옮겨줌
    - 만약 옮긴 곳에 같은 이름에 파일이 있다면 경고없이 자동으로 덮어씌어지기 때문에 주의할 필요가 있다.
- rm [파일이름] : 파일이름을 지워라
    - rm * : 현재 작업경로에 있는 모든 것을 지워라
        - 정규표현식을 이용해서 다수 작업도 가능함
    - rm sh* : sh로 시작하는 모든 파일을 지워라
    - rm *.* : directory를 제외한 모든 확장자파일을 지워라
    - rm 경로/* : 경로안에 있는 모든 파일을 지워라
    - rm -rf directory_name : directory를 삭제하고 싶을 때 사용하는 옵션



* command의 옵션을 띄어쓰기와 하이픈(-)으로 구분한다.

## vim
- 실행방법은 vim 혹은 vi를 적고 뒤에 파일명을 적으면 text파일을 수정 할 수 있게 된다.

## vim mode
- Normal mode(default) : 중심이 되는 모드로서 모든 키가 명령으로 동작한다
    - h j k l : left, down, up, right
    - i : insert mode
    - : : command line mode
    - v : visual mode
    - d : delete
    - dd : delete a line 한 줄 삭제하기
    - y : yank
    - yy : yank a line 한 줄 복사하기
    - p : paste 붙여넣기
    - u : undo 되돌리기
    - dj숫자 : 숫자만큼 커서 아래줄들 삭제
    - yy숫자 : 숫자만큼 커서 아래 복사

- Insert mode(i) : text파일을 입력, 수정이 가능한 모드
- Visual mode(v) : 블록설정, 잘 사용할 일이 없음
- Command-line mode(:) : 패턴 검색, 필터, 줄이동, 종료 등의 액션을 수행하는 모드이다.
    - :숫자 : 숫자에 해당하는 줄로 이동한다.
    - set nu : 줄마다 숫자가 표기된다.
    - q : vim을 종료한다. 변경점이 없어야만 정상적으로 실행된다.
    - q! : 변경점이 있지만 변경없이 처음 오픈했을 때로 되돌릴 때 사용된다.
    - w : 중간중간 저장하고 싶을 때 사용된다. 메모장에 Ctrl + s와 같은 기능
    - wq : 저장하고 종료

    - vim작업을 하다가 터미널을 강제 종료하면 ls -a를 통해 .swp인 스왑파일이 생성된다. 스왑파일을 제거해주면 다시 정상적으로 vim이 실행이 된다.

## Git의 주요 구성요소
- Blob : 파일 하나의 내용에 대한 정보
- Tree : Blob이나 subtree의 메타데이터(디렉토리 위치, 속성, 이름 등)
- Commit: 커밋 순간의 스냅샷 무언가를 개발하였을 때 코멘트를 남기며 변경과정에 대해 기술

- Local : 개발을 하게 되는 개발자들에 각자의 PC, server
- Remote : 여러명의 개발환경에 주요 공간이 되어주는 중심 Local에서 자유롭게 개발을 하고 Remote로 git push를 통해 업데이트하는 방식

## 그래서 Git이 그 Github랑 같은거지?
- Git은 Service가 아닌 System; Git이라는 System을 가지고 Microsoft가 Service하는게 github
    - 그 외에 service로는 오픈되면 안되는 시스템에 많이 쓰이는 gitlab, 개발 서비스를 다양하게 사용하는 프로젝트 일 때 각종 서비스 연계에 좋은 서비스인 bitbucket 등이 있다.

## How to start git with bash?
git의 환경설정을 bash에서 해주어야한다.
```bash
$ git config --global user.name "suhwankimkim" # 유저닉네임
$ git config --global user.email "marscoin8@gmail.com" # 유저이메일

$ git config --global core.editor "vim" # git text basic editor를 vim으로 setting 다른 editor로 열리면 상당히 번거로워 질 수가 있음
$ git config --global core.pager "cat" # 위와 같은 이유에서 cat을 기본 open 함수로서 사용함
``` 
git의 환경설정이 완료 되었으면 github에서 만든 repo에 주소를 복사해와 개발할 directory를 경로설정 한 후 repo를 copy해 온다. 즉 리모트를 복사해온다.

추가적인 환경설정의 수정이 필요한 경우
```bash
$ vi ~/.gitconfig #에서 값을 수정한다.
```

```bash
$ git clone [url] git bash # 햔재 위치에서 repo clone이 생성
```

```bash
$ git status # git에서 상태를 알려고 할 때 사용하는 명령어
$ git add 파일이름 # git에서 개발할려고 무언가 파일을 만들거나 수정사항이 발생하였을 때 status에서 추적이 되는데 어떠한 파일의 수정사항을 commit할건지 정할 때 사용 처음에는 README.md로 실행해준다
$ git commit # add로 올려놓은 파일을 어떻게 수정, 생성, 삭제 했는지를 적게 된다.
$ git push origin main # local에서 변경된 사항들과 commit을 REMOTE에 push 하게 된다.
```
정리하면 git status, git add README.md, git commit, git push origin main을 통해 git 상태확인, commit을 작성할 파일 올려 놓기, commit 작성, 수정사항 REMOTE에 push 순으로 진행하게 된다.
처음 github를 사용하여 git push origin main을 하게되면 계정접근을 위한 Token입력이 필요하다.
[Go to create Token!](https://github.com/settings/tokens)에 접속하여 토큰을 생성한 뒤 비밀번호 대신 복사하여 사용하면 된다.
    - MacOS에서는 값을 입력해도 입력여부가 보이지 않는다.

## How to write commit ?
commit은 개발하면서 어떤 의도를 가지고 개발을 하는지를 알 수 있는 좋은 도구이지만 기록을 제대로 하지 않으면 여러명이 동시에 하는 프로젝트인 경우에는 혼란을 야기할 수 있다. 따라서 일정한 commit 작성 규칙이 있다.

- commit은 1줄이 제목이며 제목을 작성하지 않으면 안된다.
- commit에 내용은 1줄 이후 3번째 줄부터 작성하면 된다. 보통 제목으로 내용을 알 수 있게 작성이 되어있어 내용은 잘 작성하지 않는다.
- Merge를 통해 충돌이 일어난 파일은 작성을 생략하여도 된다.

1. commit의 제목은 commit을 설명하는 문장형이 아닌 구나 절의 형태로 작성한다.
2. importanceofcapitalize 'Importance of Capitalize' 중요한 단어 첫 알파벳은 대문자
3. prefix 꼭 달기 무슨 종류의 commit인지 대략 구분할 수 있는 구분을 달아주기
    |Prefix|내용|
    |---|---|
    |feat|기능 개발 관련|
    |fix|오류 개선 혹은 버그 패치|
    |docs|문서화 작업|
    |test|test 관련|
    |conf|환경설정 관련|
    |build|빌드 작업 관련|
    |ci|Continuous Integration 관련|
    |chore|패키지 매니저, 스크립트 등|
    |style|코드 포매팅 관련|

## github를 통해 프로젝트를 시작한다면 반드시 해야하는 작업!!
여러명이 함께 github를 통해 개발을 한다면 각자 개발하는 local에 os가 어떤사람은 가상환경 어떤사람은 window 또 어떤사람은 Mac인경우 각자 os에서만 실행되는 파일이라던지 aws server를 open할 때 사용되는 key.pem 파일이라던지 중요한 민감정보와 같은 것들이 같이 push될 수 있다. 이러한 상황을 막기 위해서 예외 처리를 해야하는데 다음과 같이 할 수 있다.

```bash
$ mkdir .gitignore # 특정 파일이나 디렉토리를 추적하지 않도록 명시하기 위한 파일
$ vi .gitignore # 어떤 파일을 예외처리 할건지에 대한 설정을 직접해야한다.
```
어떤 파일을 예외처리 할건지에 대한 설정은 [Go to create .gitignore](https://gitignore.io/)에서 할 수 있다. 자신이 사용하는 언어 환경 등을 추가하면 적절한 .gitignore를 작성해주므로 복사 붙여넣기만 하면된다.

## git with .ipynb
옛날에는 jupyter notebook을 통해 수정이 이루어지면 뭐가 바뀌었는지 변경사항을 추가적인 변환을 통해 일일이 찾아 주었지만 요새 github에서 제공되어지는 옵션을 통해 github에서 무엇이 바뀌었는지 심지어 그래프에 변화도 비교해서 추적가능하다.

## pre-commit
* commit 수행 전 체크해야 할 것들을 자동으로 수행하도록 도와주는 도구이다.
* 보통 add인 상황에서 사용되며 파일의 불필요한 공백같은 것을 알아서 제거해주거나 충돌이 일어나면 자동으로 병합해준다.

```bash
$ pip install pre-commit
$ pre-commit --version
$ touch .pre-commit-config.yaml
# after setting configuration
$ pre-commit install
$ pre-commit run --all-files
```

## **Branch**
- commit이 시간이라면 Branch는 공간에 해당한다. 따로 독립적인 분리된 공간을 만들어서 매우 공격적인 개발을 할 수 있게 해주는 강력한 도구
```bash
# Branch list
$ git branch # local branch check
$ git branch -r # remote branch check
$ git branch -a # all branch check

# Create new branch
$ git branch [branch name] # branch name으로 된 branch 생성

# switch to branch
$ git switch [branch name] # branch name으로 된 branch로 작업경로 변경

# Delete branch
$ git branch -D [branch name] # branch name으로 된 branch 삭제
```

- 반드시 주의할 점으로 브랜치를 넘나들 때는 반드시 해당 브랜치에 커밋이 끝난상태이여야 한다.!!!
    - origin/HEAD : HEAD는 최근, 최신이라는 의미로 최근의 쓰여진 commit이나 branch를 의미한다. 깃허브에 리모트 주소를 일일이 표현해줄 수가 없어서 origin이라고 표현하여 remote주소를 표현해준다. 
    - branch에서 작업한게 마음에 들면 병합하면 된다. main branch로 넘어와 git merge [branch name]으로 병합해주면된다.

## Merge conflict
- 병합을 하다보면 branch를 만들고 독립적으로 main도 commit하고 branch도 commit을 한다면 branch에는 main에 commit에 대한 정보가 없어서 충돌하게 된다. 이럴 때 해결하는 2가지 방법

    1. Use to revase : branch에 변경된 main에 정보를 주는 방법이다. 잘 사용하지는 않고 main에서 개발한 내용이 branch에 필요한 경우에만 사용된다.
    2. Use to merge : Merge를 그냥 진행하게 된다면 충돌이 일어난 파일에 충돌이 어디서 일어나는지 표기가 되게 된다. <<<<, >>>>>, ======과 같은 부분을 제거하고 어떻게 병합할 것인지 합의 후에 수정

- 추가적인 **주의**점 git commit -m '내용'을 통해 vim text editor모드에 들어가지 않고 cli상태에서 commit은 가능하지만 merge된 파일은 head부분이 이미 작성되어 있기 때문에 굳이 작성해줄 필요가 없다 오히려 이러한 command로 인해 Merge된 파일인데 commit을 통해 알 수 없어지게 된다면 프로젝트를 참가하거나 나중에 내가 보았을 때 구분을 할 수 없어 혼란을 야기 할 수 있다.





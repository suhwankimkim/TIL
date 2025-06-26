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

```bash
$ git clone [url] git bash # 햔재 위치에서 repo clone이 생성
```

```bash
$ git status # git에서 상태를 알려고 할 때 사용하는 명령어
$ git add 파일이름 # git에서 개발할려고 무언가 파일을 만들거나 수정사항이 발생하였을 때 status에서 추적이 되는데 어떠한 파일의 수정사항을 commit할건지 정할 때 사용
$ git commit # 







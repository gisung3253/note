	ID : gisung3253@naver.com
	PASSWORD : Park3253!

	![[Pasted image 20240309163000.png]]
	git과 github는 다른 개념이다.
	우선 버전 관리 개념에 대해 정리해보자.

### 버전 관리
	개발 경험이 없더라도 누구나 한 번쯤은 버전 관리의 경험이 있을 것이다.
	게임을 진행하다가 게임을 종료하기 전에 지금까지 진행한 게임 데이터를 저장한다.
	그리고 다시 게임을 시작할 때는 이전에 저장한 데이터를 불러와 게임을 이어서 한다.
	게임과 같은 혼자 사용하는 프로그램이라면 버전 관리 시스템이 없어도 버전 관리를 할 수 있다. 
	하지만 여러사람이 함께 만드는 프로그램에서는 어떡해야할까?
	
	팀 프로젝트에서 사용 할 공용 폴더를 만들고 그곳에 소스 코드를 올려놓는다고 가정하자.
	이곳에 올려진 최초의 소스 코드를 '0버전' 이라 가정하자.
	팀원 A가 '0버전'의 소스 코드를 수정하여 '1버전' 으로 저장하고,
	팀원 B가 '1버전'을 수정하여 '2버전'으로 저장할 수 있을 것이다.
	
	팀 프로젝트에 참여하는 인원이 많을수록, 혹은 프로젝트 기간이 길수록 파일 관리나
	어느 파일이 최종 업데이트 파일인지 확인하는 것 등 여러 문제가 많아진다.
	그래서 협업 프로젝트에서는 버전 관리가 필수적이다.

### Git 과 GitHub
	정리하면 Git은 버전 관리 시스템이고 
	GitHub는 Git으로 관리하는 프로젝트를 올리는 코드 저장소이다.
git은 버전관리 도구
변경된 내용만 정리
코드를 언제 누가 변경했는지 비교 가능

github는 코드 저장소


git 설치법
https://git-scm.com/
![[Pasted image 20240309174125.png]]
운영체제에 맞춰서 다운로드
다른 선택 필요없이 전부 next

다운로드 후 git bash 열어주기
![[Pasted image 20240309174824.png]]

git 환경설정

- git config --global user.name "~"
- git config --global user.email "~"
- git config --list (config 잘 되었는지 확인)

![[Pasted image 20240309175403.png]]

코드 올리기
![[Pasted image 20240309175535.png]]

내 코드에서 터미널 열기

- git init
![[Pasted image 20240309180457.png]]

- git add . (. 은 전부 다 라는 뜻, git add는 어떤 파일을 올릴지 추려본다)
- git add index.html (이 파일 하나만 올린다는 뜻)
- git status
![[Pasted image 20240309180701.png]]

히스토리 만들기
- git commit -m "~" (히스토리를 만드는것 ex. 과제 1, 2,3)

git허브와 연결시키기
git remote 복사해서 프로젝트 터미널에 붙여넣기
![[Pasted image 20240309181027.png]]
이 repository로 내 소스코드를 보낸다는 뜻
![[Pasted image 20240309181212.png]]

- git remote -v (연결확인)
![[Pasted image 20240309181432.png]]

- git push origin master (파일 github로 보내기)
![[Pasted image 20240309181647.png]]

만약 코드를 바꿨다면?
- git init 은 초기화여서 할 필요 없음
- git add .
- ![[Pasted image 20240309182215.png]]
- git commit -m "~"
- git push origin master
- ![[Pasted image 20240309182342.png]]
- ![[Pasted image 20240309182421.png]] 
- 어떤 부분이 추가됐는지도 확인 가능

코드 다운받기
![[Pasted image 20240309183030.png]]
code 버튼 누르기
![[Pasted image 20240309183053.png]]
복사

명령프롬프트창 열기
- git clone ~
![[Pasted image 20240309183430.png]]
- code . (실행)

동기화
- git add .
- git commit -m "~"
- git pull origin master (새로운 코드를 받아온다)
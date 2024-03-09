	ID : gisung3253@naver.com
	PASSWORD : Park3253!


![[Pasted image 20240309163000.png]]
git과 github는 다르다.

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
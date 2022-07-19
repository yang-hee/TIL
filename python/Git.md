# git : 버전관리 시스템

- 실제폴더 / working directory  staging area / commits으로 구성
  - **working directory**
    - 내가 작업하고 있는 공간
    - git add 시 자동적으로 올라감
  - **staging area**
    - 작업물을 남겨놓는 임시 공간
    - git add 시 staging area에 올라간다
  - **commits**
    - 작업물 올림

## **초기설정(config) : 기록을 남기기 위함**

- **config = 설정**
- **git config --global user.name 내이름**
  - 내 Git_Hub 이름 설정
  - global 하면 내 컴퓨터 전체에 설정
- **git config --local user.name 내이름** 
  - local : 설정한 폴더에만 적용
- **git config -- global user.email 내메일주소**
  - 내 Git_Hub 메일 주소 설정
- **git config --global -l**
  - git 설정 알려줌
  - user.name / user.email 확인가능

## **git init**

- git으로 폴더 관리 시작
  - Git bash에서 master로 표시가 된다

## **git status**

- 내 상태 확인하는 것
  - 수정할 때 마다 확인해주자. 자주자주 확인할 것

<**a.txt** 파일이 실제폴더에는 존재하지만 아무상태도 아님

(staging area에 존재 하지 않음-add를 하지 않았기 때문)>

## **git add**

- **git add 파일이름.확장자**
  - staging area에 해당 파일을 올린다.
  - working directory에도 존재
- **git add .**
  - 내 폴더에 있는 **모든 파일**을 staging area에 올림

<a.txt 파일이 git으로 관리가 되고있고 commit할 준비가 되어있다.>

## **.gitignore**

- git 연동하자마자 제일먼저 해줄 것!!!!!
  - gitignore.io
- touch .gitignore하고 .gitignore 파일에 포함하고 싶지 않은 파일명 적는다 여러개 하고싶으면 엔터로 구분한다.
- 맨처음 add/commit을 하기전에 지정해야 가능함.

## **git commit**

- **git commit -m 'commit message'**
- 커밋(버전기록 남기기)
  - staging area에서 파일이 commit으로 넘어오는 것
  - commit message는 변경 가능, 필수.
    - **git commit**만 쳤을 때
      1. **VI모드** 접근
      2. **I** 누르면**INSERT**로 바뀜
      3. 노란텍스트 : 제목 / Enter로 줄바꿈 / 하얀텍스트 : 내용
         - 여러줄 작성가능
      4. **ESC**로 INSERT 탈출 후 **:wq**입력하면 **VI모드 종료**

## **git log**

- commit 기록 확인
- **git log --oneline**
  - 깔끔하게 commit 기록 확인. commit message/commit id 보여줌
- **git log -숫자**
  - 숫자 갯수 만큼의 로그만 보여줌
  - 숫자가 2면 2개의 로그만

## **git hub와 연동**

### **하나의 git에 하나의 git hub 연결**

```
git remote add origin https://github.com/yang-hee/git-practice.git
```

- **git remote add 별명 url**
  - 별명 : url의 별명
  - 내 git과 git hub 연동 / 파일 올릴 수 있게
- **git remote rm 별명**
  - 별명 연동 해제
- **git push -u origin master**
  - 여러공간에서 작업할 때 작업물을 올리기 위해 사용
  - master를 origin에 push함
  - origin = remote 이름 / 변경가능
  - master = branch 이름 / 변경가능
  - u : 계속 같은 경로로 푸쉬해준다..?
    - u를 한번 해주면 다음번에 git push만 해도 됨
- **git clone url**
  - url 레포지토리의 파일들을 복제함 가져옴.
  - 처음 폴더를 생성할 때만 사용
- **git clone url .**
  - 내 위치에 복제함. 새 폴더로 만들지 않음.
- **git clone url 폴더이름**
  - 폴더이름으로 폴더변경해서 생성
- **git pull**
  - 여러공간에서 작업할 때 작업물을 가져오기 위해 사용

### **기타 명령어**

- git restore --staged
  
  - staging area 에서 working directory로

- mv 파일1 파일2
  
  - mv text.txt a.txt
    - a.txt에서 text.txt로 이름 변경

- ctrl + l
  
  - git bash에서 마지막 명령어만 보이게 해줌 => 화면정리
    
    git과 clone의 충돌시

## git과 clone 충돌시

- **abc/abd 충돌**
  
  - pull시 : wq로 탈출해서 머징

- **a’bc/abc 충돌**
  
  - CONFLICT
  
  - pull시 : vs코드(code .)로 들어가서 a’와 a중 택1
    
    add commit push!

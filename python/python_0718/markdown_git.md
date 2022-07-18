# 마크다운 / git

# **마크다운**

- # 내용 : 제목
- ## :부제목
- #개수에 따라 크기 다르다
- # 6개 까지 가능
- [toc]
    - 목차
    - 노션에서는 /toc

## **강조표시**

- **볼드처리** **bold**
    - Ctrl + b
- *기울기* *italic*
    - Ctrl + i
- ~~가운데 줄~~ ~~line~~

## **리스트**

- 리스트 (- 스페이스바) unordered list
    - tab (들여쓰기)
        - tab (들여쓰기)
    - shift+tab (내어쓰기)
- \ : escape sequence 문자그대로 사용. 명령어 적용X -
- \n : 줄바꿈
1. (숫자 + . + 스페이스바) ordered list

## **코드블록**

- **inline codeblock**
    - **`코드`**
    - `코드`
- **code block**
    - **```+스페이스바 언어**
    - ``` python 하면 파이썬 코드블럭 생성

```
this is python code
```

## **링크**

- [네이버](https://www.naver.com/)
- **[보여줄단어](url주소)**

## **이미지**

- !+[이미지가 없을 때 나오는 문자](이미지 주소)
- 
    - 공식문서의 설정 반드시 하기!
    - 상대주소 사용하는 이유
        - md파일을 다른데 업로드 할 때 .assets도 같이 업로드하기

## **구분선**

- --

---

## **표**

1. **|컬럼1|컬럼2|컬럼3|** *| => shift +\
2. ctrl + t로도 표 생성 가능

[제목 없음](https://www.notion.so/2c24de937f94458793af151e9dc620da)

## **인용문구**

> 이것은 인용문구 입니다.
> 
- > + 스페이스바
- 중첩 가능
    - 노션에서는 " + 스페이스바

# **git**

버전관리

- 실제폴더
- working directory
    - 내가 작업하고 있는 공간
    - git add 시 자동적으로 올라감
- staging area
    - 작업물을 남겨놓는 임시 공간
    - git add 시 staging area에 올라간다
- commits
    - 작업물 올림

## **초기설정(config)**

- **config = 설정**
- **git config --global user.name 내이름**
    - 내 Git_Hub 이름 설정
- **git config --local [user.name](http://user.name) 내이름** : gitlab이랑 github 주소 다를때 해주기!!
- **git config -- global user.email 내메일주소**
    - 내 Git_Hub 메일 주소 설정
- **git config --global -l**
    - git 설정 알려줌
    - user.name / user.email 확인가능
    

***git lab 할때는 local로/git hub 할때는 global로!

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

- git restore --staged <file>
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
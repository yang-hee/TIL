# module

다양한 기능을 하나의 파일로 묶은 것 **(module)** -> 다양한 파일을 하나로 폴더로 묶은 것 **(Package)** -> 다양한 패키지를 하나의 묶음으로 묶은 것 **(library)** -> 관리 **(pip)**

## **모듈**

- 특정 기능을 하는 코드를 파이썬 파일 단위로 작성한 것

- 외부 개발자들의 코드를 가져다 쓰기 위한 방법

### 모듈 불러오기

- import module

- from module import var, function, Class

- from module import *

## **패키지**

- 모듈을 모은 것

- \_\_package-name\__

### 패키지 불러오기

- from package import module

- from package.module import var, function, Class

### 파이썬 패키지 관리자(pip)

외부 사람들이 만든 기능을 받아 올 수 있다.

- $pip install SomePackage : 최신버전의 패키지 설치

- $pip uninstall Somepackage : 패키지 삭제

- $pip list : 내가 갖고있는 패키지

- $pip show SomePackage : 패키지의 정보

**내 패키지를 작업환경이 바뀌어도 사용할 수 있게 함**

- $pip freeze >requirements.txt : >파일명 으로 내 현재 패키지를 박제 할 수 있다.

- $pip install -r requirements.txt : >파일명에 박제된 내 패키지들 설치

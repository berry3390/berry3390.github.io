---
layout: post
title: ChangePermissionFiles
---

# 파일 권한 변경하기 

### 터미널 사용법
- 기본 권한  
  - sudo : 관리자
  - 보통 관리자 유저
- 옵션 사용
  - 글자 하나 : -
  - 단어 : --
- 도움말 보기
  - 명령어 --help : 간략한 도움말
  - man 명령어 : 상세 도움말 manual
  - / : 검색
  - n : 다음
  - shift + n : dl
  - [] : 옵션
- -v
  - verbose
  - log보는 옵션
- ls -al
  - 디렉토리 내 모든 파일 정보 출력
  (파일 타입, 퍼미션정보, 링크수, 소유자, 소유그룹, 용량, 생성날짜, 파일이름)


### ssh접속하기
```
ssh -i ./xx.pem username@servername
```
- username를 지정하지 않으면 컴퓨터 계정의 이릅을 넣는다.
- 파일 지정할 때  ‘./‘ 를 사용하는게 좋다. (os별로 경로를 못찾는 경우 있음. 솔라리스 등)  

### 리눅스 파일권한
사용 이유 : 서버의 경우 계정 단위를 어플리케이션으로 두기도 한다. (ex. http용, node용)

##### 권한 표기
- 사용자/그룹/그외 d(directory) rwxrwxrwx로 표기된다. `drwxr-xr-x`
- 각 종류는 읽기(r), 쓰기(w), 실행권한 executor(x)이 있다.
  ( 디렉토리, 실행파일의 경우 executor권한이 필요하다. )

### 권한 변경
- chown 소유자 변경
- chmod 9자리글자(rwxrwxrwx)로 파일 권한 변경
  - 각 권한 여부를 2진수로 변경 (ex. 101)
  - 종류별로 끊어서(111, 111, 111) 10진수로 변환


### 10진수 변환 예 (111)
- 시그마 n * 2^n
 = 0 자릿수 값 (1) * 2^0 + 1자릿수값 (1) * 2^1 + 2자릿수값 (1) * 2^2
 = 1 + 2 + 4 = 7


## chown 명령어 익히기
```
usage: chown [-fhv] [-R [-H | -L | -P]] owner[:group] file ...
       chown [-fhv] [-R [-H | -L | -P]] :group file ...
```

chown hyejin ./a
chown hyejin:group1 ./a
chown -v -R :group1 ./


## 소스폴더에 있는 것들 한 명령어로 한번에 같은 권한으로 수정
- -R
  - L : 모든 파일 변경
  - H :
  - P :
- chmod -v -R -L 700 ./

---
layout: post
title: ChangePermissionFiles
---

# 파일 권한 변경하기 

## 터미널 사용법
- - : 글자 하나일 경우 
- -- : 단어일 경우 
- -v
  - verbose
  - log보는 옵션
- / : 검색
- n : 다음
- shift + n : 이전 
- [] : 옵션
- 도움말 보기
  - 명령어 --help : 간략한 도움말
  - man 명령어 : 상세 도움말 manual
- ls -al
  - 디렉토리 내 모든 파일 정보 출력
  (파일 타입, 퍼미션정보, 링크수, 소유자, 소유그룹, 용량, 생성날짜, 파일이름)
  ```
  drwxr-xr-x+   72 hyejin  staff   2448  2  7 00:24 .
  drwxr-xr-x     7 root    admin    238  2  7 01:05 ..
  ```

## 리눅스 파일권한 
> 서버의 경우 계정 단위를 어플리케이션으로 두기도 한다. (ex. http용, node용)

### 권한 변경 
#### 권한 표기 
`drwxr-xr-x    16 hyejin  staff    544  1 18 16:41 .atom`

#### chown : 소유자 변경 
```
usage: chown [-fhv] [-R [-H | -L | -P]] owner[:group] file ...
       chown [-fhv] [-R [-H | -L | -P]] :group file ...
```
```
chown hyejin ./a
chown hyejin:group1 ./a
chown -v -R :group1 ./
```

#### chmod : 9자리글자(rwxrwxrwx)로 파일 권한 변경
- 맨 앞자리 타입 (d: directory, l: link) 
- 사용자/그룹/그외 rwx/rwx/rwx
- x: 실행권한 executor
    디렉토리, 실행파일의 경우 필요하다.

##### 변경 방법 
1. 사용자, 그룹, 그외 세자리씩 끊는다.
2. r, w, x 각 권한 여부를 2진수로 변경 (ex. 101)
3. 10진수로 변경하여 합친다. 

###### 10진수 변환 예 (111)
- 시그마 n * 2^n
 = 0 자릿수 값 (1) * 2^0 + 1자릿수값 (1) * 2^1 + 2자릿수값 (1) * 2^2
 = 1 + 2 + 4 = 7
 
## 소스폴더에 있는 것들 한 명령어로 한번에 같은 권한으로 수정
- `-R` 
  - `-L`: all symbolic links are followed.
  - `-H`: symbolic links on the command line are followed.  
        Symbolic links encountered in the tree traversal are not followed.
  - `-P`: no symbolic links are followed.
        Instead, the user and/or group ID of the link itself are modified.
        This is the default. Use -h to change the user ID and/or the group of symbolic links.
  - symbolic links: 윈도우의 바로가기, 맥의 가상본 
  - **Note:** 옵션 H와 P의 차이
- chmod -v -R -L 700 ./

## ssh접속하기
```
ssh -i ./xx.pem username@servername
```
- username를 지정하지 않으면 자동으로 컴퓨터 계정의 이릅을 넣는다.
- 파일 지정할 때  ‘./‘ 를 사용하는게 좋다. (솔라리스 등 os에 따라서 ./를 지정하지 않으면 경로를 못찾는 경우가 있다.)  

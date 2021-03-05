## 정리

- 쉘
+ 리눅스 에서는 Bourne-Again Shell (bash)를 많이 사용함
+ GNU 프로젝트의 일환으로 개발됨, 리눅스 거의 디폴트 쉘임
- user 관련 명령: whoami, useradd, adduser, passwd, su - {username}
- Directory/file 관련 명령 : 
    + pwd 경로 확인
    + cd 경로 이동 (cd ~ 루트 파일, cd - 이전 파일)
    + ls 옵션으로 -al 사용 
    + cat {파일명} 파일 내용을 보기 위해 vi를 사용하기도 하지만 cat 사용시 터미널에서 확인 가능
    + head/tail {파일명} 앞뒤 10줄을 보여줍니다.
    + more {파일명} 한 화면에서 파일 내용을 보여줍니다. 엔터는 한줄 이동, 스페이스는 화면 크기만큼 이동
    + rm {파일명} 파일 삭제
- Directory/file 권한 관련 명령 : chmod, chown, chgrp
- 관리자 권한으로 실행하기 : sudo
- 다양한 옵션은 man 명령으로 메뉴얼 확인

## Standard Stream (표준 입출력)
* command로 실행되는 프로세스는 세 가지 스트림을 가지고 있음
  - 표준 입력 스트림(Standard Input Stream)  **stdin**
  - 표준 출력 스트림(Standard Output Stream)  **stdout**
  - 오류 출력 스트림(Standard Error Stream)  **stderr**
* 모든 스트림은 일반적인 plan text로 console에 출력하도록 되어 있음

## 리다이렉션 (redirection)
* 표준 스트림 흐름을 바꿔줄 수 있다.
   + \> , < 기호를 사용함
   + 주로 명령어 표준 출력을 화면이 아닌 파일에 쓸 때 사용

* 예
1. ls > files.txt
      - ls로 출력되는 표준 출력 스트림의 방향을 files.txt로 바꿔줌
2. head < files.txt
- files.txt의 파일 내용이 head라는 파일의 처음부터 10라인까지 출력해주는 명령으로 넣어짐
3. head < files.txt > files2.txt
   - files.txt의 파일 내용이 head로 들어가서 files.txt의 앞 10라인을 출력
     - head의 출력 스트림은 다시 files2.txt로 들어감
4. 기존 파일에 추가는 >> 또는 << 사용
- ls >> files.txt
  - 기존에 있는 files.txt 파일 끝에 결과를 출력

## 파이프 (pipe)
- 두 프로세스 사이에서 한 프로세스의 출력 스트림을 또 다른 프로세스의 입력 스트림으로 사용할 때 사용됨
1. ls | grep files.txt
   - ls 명령을 입력한 출력 내용이 grep 명령의 입력 스트림으로 들어감
   - grep files.txt는 grep 명령의 입력 스트림을 검색해서 files.txt가 들어있는 입력 내용만 출력해줌

## 프로세스 명령어

- sudo apt-get install gcc : C언어 컴파일러 설치
-  vi loop.c -> 무한 루프 파일 생성
-  gcc loop.c -o loop -> loop 실행 파일 생성
- ./loop -> loop 파일 실행
- ./loop & -> 새로운 프로세스에서 실행
- ctrl + z : 프로세스 중지
- ctrl + c : 프로세스 종료
- jobs : job 보기
- bg : 중지된 프로세스 실행
- ps : 프로세스 보기, 옵션 aux 추가시 프로세스 상세 정보 보기
- kill -9 {프로세스 ID} :  -9는 강제로 프로세스를 없앨 수 있는 옵션
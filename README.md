## 시스템 명령어
hostname : ip 주소
whoami : groot0 현 로그인 된 유저 네임
pwd(print working directory) : 실행되고 있는 디렉토리 알려줘 `/home/groot0`
cd : 전 디렉토리로 가기 `/home`
id : 현 유저에 대한 식별 정보 출력 (사용자 아이디, 속한 그룹 아이디)
uname : 들어와있는 시스템 정보 ( 운영체제 이름, 버전, 타입 등)
     -a : 전체 정보 열람 가능
     -r : 커널의 릴리즈 버전 출력
man(manual) : 뒤에 다른 명령어 치면 해당 명령어 사용 설명서 나옴
clear : 작업 화면 리셋

## 읽기 명령어
### groot 0
ls : 현재 있는 디렉토리에 어떤 파일 or 폴더 있는지 보여줘
	 -l : 폴더인지 파일인지 판별
cat(concatenate) + 파일 명 : 파일 읽기
	 --help : 명령어 설명
	 파일1 > 파일 2 : 파일 1을 파일 2에 합치기
### groot 1
cd(Change Directory) 파일 or 폴더 명 / : 해당 디렉토리로 옮겨가기 (.. 은 전 디렉토리)
\* flag = 비밀번호

### groot 2
cd + 파일 or 폴더 명에 띄어쓰기있을 때
	 띄어쓰기 자리에 `\ + 띄어쓰기`
	 첫 글자 입력 후 `Tab` 누르기 > 자동 완성
	 `" "` or `' '`로 감싸기

### groot 3
ls 했을 때 아무것도 안뜸 > 히든 파일 확인 하기
	 -a : 히든 파일 나옴 (히든 파일은 앞에 `.` 붙어 있음)

### groot 4
ls 했을 때 큰 용량 파일일 때
less 파일 or 폴더 명 : 새 탭창에서 파일 내용 만 볼 수 있음
head : 큰 파일을 읽거나 어떤 종류의 파일 알고 잎을 때 1~10 번째줄만 출력
	 -n (숫자) : 숫자 번쨰 줄 까지 출력
tail : 마지막 10개의 줄만 출력
	 -n (숫자) : 마지막부터 숫자개의 줄 출력

## 쓰기 명령어
### groot 5
ls > permission denied
	 -al : permission denied 된 이유 찾아보기
touch + `이름`: `이름` 파일 만들어 줌
echo `'문구'` > 파일명 : 파일에 `'문구'` 가 들어감
cp(copy) `파일1` `파일2` : 파일1을 복사해서 파일2 생성
mv(move) `파일명` `디렉토리명` : 파일 이동 및 파일 이름 변경
mkdir(make directory) `newfolder` : 현재 디렉토리 안에 새 폴더 추가
rm(remove) : 삭제
	 -r : 폴더 삭제
groups `username` : 유저가 어느 그룹 안에 있느냐

첫번째 비트
		d (directory) : 폴더
		\-  : 파일
다음 9비트
	 첫번쨰 3비트 : 유저 대한 권한
		 r(read) = 4 : 읽기 가능
		 w(write) = 2 : 쓰기 가능
		 x(ececution) = 1 : 실행 가능
		 유저한테 rw-권한 주고 싶을 때 4+2=6
		 chmod `600(3비트씩 나눔)` `파일명` : 권한 수정 가능
	 두번째 3비트 : 그룹 대한 권한
	 세번째 3비트 : 그 외 유저들 대한 권한

### groot 6
base64 `파일명` : 민감한 정보 디코딩 해서 랜덤한 스트링으로 저장 하고 싶을 때
	 `파일1` > `파일2` : `파일1` 인코딩해서 `파일2`에 저장 가능
	 -d : 디코딩 하고 싶을 때 (디코딩 했는데도 랜덤 스트링일 때 : 여러번 인코딩 된 거임)
\| : 한 명령어의 출력을 다른 명령어의 입력에 전달 할 때 사용
	 base64 -d file.txt | base 64 -d : 디코딩 두번 할 때 처음 디코딩한 결과를 두번째 디코딩의 입력으로 전달 할 때
grep `"찾을 단어"` : 해당 단어가 들어간 파일 찾음
	 ls | grep "password" : 현 디렉토리 안의 password라는 단어가 들어간 파일 or 폴더 출력

\>(redirector) : 아웃풋 옮길 때
	 ls > test.txt : 현 디렉토리 ls 값을 test 라는 파일에 바로 저장 가능
	 echo "world" > output.txt : output.txt의 내용과 상관 없이 덮어 씌우기
	 echo "world" >> output.txt : output.txt에 내용 추가

fin

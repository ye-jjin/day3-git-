# day3 - git 명령어

### git init
- 새로운 Local Git 저장소를 생성하는 명령어 입니다.
- 디렉토리를 만든 후, 그 안에서 명령어를 실행하면 .git 하위 디렉토리가 생성됩니다.

<br/>
<br/>

- 실습 순서
1. `test` 디렉토리 생성
2. `red`, `orange` 파일 추가
3. `test` 디렉토리를 로컬 저장소로 설정

<br/>
<br/>

- 실습 코드

![git init](https://user-images.githubusercontent.com/122597068/226675682-d8b59390-005c-40c7-a942-30fde177e6e9.png){: width="100%" height="100%"}

<br/>
<br/>


- 실습 결과

![git init 1](https://user-images.githubusercontent.com/122597068/226675849-d0ea1f14-e922-44de-b595-8a5926168f72.png)

---

### git status

- 현재 작업 중인 파일의 상태를 확인하는 명령어입니다.

<br/>
<br/>

- 실습 순서
1. `git status` 입력 혹은 `gst`  입력

<br/>
<br/>

- 실습 코드 및 결과

![git status](https://user-images.githubusercontent.com/122597068/226676343-41d40957-8edb-4102-8c4d-743bd54a117a.png)

- `orange`와 `red` 가  untracked files( 추적하지 않는 파일) 로 존재

---

### git add
- 인덱스에 커밋할 파일의 변경 사항을 저장할 수 있는 명령어입니다.

|명령어|기능|
|---|---|
|$ git add <파일명>|커밋에 단일 파일의 변경 사항을 포함|
|$ git add *|커밋에 파일의 변경 사항을 한번에 모두 포함|
|$ git add -A|커밋에 파일의 변경 사항을 한번에 모두 포함|

<br/>
<br/>

- 실습 순서
1. `A` 옵션을 이용하여 전체 파일(`orange`, `red`)을 인덱스에 추가
2. 상태 확인

<br/>
<br/>

- 실습코드 및 결과

![git add](https://user-images.githubusercontent.com/122597068/226676591-35386def-a024-4bd6-8de6-4101d0a05b85.png)

- untracked files에 있던 `orange`와 `red`의 상태가 변경된 것을 확인

---

### git commit
- 인덱스에 추가된 변경 사항을 확정하는 명령어입니다.

- 실습 순서
1. `git commit - m "커밋 메세지"`    이용하여 커밋 생성

<br/>
<br/>

- 실습 코드 및 결과

![git commit](https://user-images.githubusercontent.com/122597068/226676782-1cb470be-4d59-41f3-acf1-529b4a2b78cd.png)

---

### git log
- 커밋의 내용 및 이력을 확인 할 수 있는 명령어입니다.

<br/>
<br/>

- 실습 코드 및 결과

![git log](https://user-images.githubusercontent.com/122597068/226677032-6d0523ce-41d3-4ddf-97b1-771deb47ffc8.png)

---

### git reset
- 특정 커밋까지의 이력을 초기화하는 명령어입니다.

- 실습 순서
1.  `git reset <커밋 아이디> -- hard`  로 이력 초기화
2.  `git log`로 이력 삭제 확인

<br/>
<br/>

- 실습 코드 및 결과 

![git reset](https://user-images.githubusercontent.com/122597068/226677545-6a552a85-1255-40e0-8ffb-580bc7844ffd.png)

- 이전의 3번째 커밋 이력이 사라진 것을 확인

---

### git swith -c
- 새로운 브랜치를 생성하고 이동하는 명령어입니다.

|명령어|기능|
|---|---|
|$ git branch <브랜치이름>|브랜치 생성|
|$ git swtich <브랜치이름>|브랜치 이동|
|$ git swtich -c <브랜치이름>|브랜치 생성과 이동|

<br/>
<br/>

- 실습 순서
1. `git swtich -c <브랜치이름>`으로 브랜치를 생성하면서 이동
2. `git swtich master` 로  브랜치 이동

<br/>
<br/>

- 실습 코드 및 결과

![git switch](https://user-images.githubusercontent.com/122597068/226678006-e3f936c7-f622-4ceb-86c8-c477aefa8355.png)

![git switch 변경](https://user-images.githubusercontent.com/122597068/226678141-711b0ffe-92c0-4dc5-bb7b-e97f85e0edc3.png)

---

### git merge
- 현재 브랜치에 다른 브랜치의 수정 사항을 합치는 명령어입니다.

<br/>
<br/>

- 실습 순서
1. `add-color` 브랜치에 파일 내용 변경
2. 전체 변경사항을 인덱스에 추가
3. 커밋
4. `master` 브랜치로 이동
5. `add-color` 브랜치의 수정사항을 `master` 브랜치로 머지
6. 전체 커밋 메시지 확인

<br/>
<br/>

- 실습 코드 및 결과

![git switch 1](https://user-images.githubusercontent.com/122597068/226678653-214d1401-bdee-41a9-82cc-b361069f852a.png)

![git switch 2](https://user-images.githubusercontent.com/122597068/226678817-e8e7f53a-4243-4892-9d5f-2fada4eae841.png)

![git merge](https://user-images.githubusercontent.com/122597068/226679088-0e1caf66-c084-4b49-a689-a7a75dc8d86f.png)

---

### conflict
- 두 브랜치의 동일한 파일에 상반된 내용이 있을 때, 충돌이 나타나는데 충동을 해결하고 커밋을 하거나, 머지 작업을 취소 할 수 있습니다.
- 머지 작업을 취소할 때 사용하는 명령어는 `git merge --abort` 입니다.

<br/>
<br/>

- 실습 코드 및 결과

![conflict](https://user-images.githubusercontent.com/122597068/226679437-174133e1-2ad9-4ab8-a331-75ece162a0e8.png)

![git abort](https://user-images.githubusercontent.com/122597068/226679654-ddac5276-9ff1-49d4-885e-23c0ddaf5499.png)

---

### git push
- 로컬 저장소에 있는 커밋 목록을 원격 저장소에 저장하는 명령어 입니다.

<br/>
<br/>

- 실습 순서
1. `git remote add origin <등록된 원격 서버 주소>` 로 git에게 새로운 원격 주소를 등록
2. `git push origin master` 로  변경 사항 원격 서버에 업로드

<br/>
<br/>

- 실습 코드
이미지
- 실습 결과
이미지

---

### git clone
- 원격 저장소를 로컬 저장소로 복제하는 명령어입니다.

<br/>
<br/>

- 실습 순서
1. 새로운 디렉토리를 생성하기 위해 상위 디렉토리로 이동
2. `test-2` 디렉토리에 원격 저장소를 복제

<br/>
<br/>

- 실습 코드
이미지
- 실습 결과
이미지

---

### git pull
- 원격 저장소의 변경된 목록을 로컬 저장소로 가져오는 명령어입니다.
- Git은 자동으로 원격 저장소와 로컬 저장소를 동기화하지 않기 때문에, 명령어를 입력해야 합니다.

<br/>
<br/>

- 실습 순서
1. `test` 디렉토리로 이동
2. `purple` 파일 추가
3. 전체 파일 인덱스에 추가
4. 새 커밋 작성
5. 원격 저장소에 푸시
6. `test-2` 디렉토리로 이동
7. 원격 저장소 풀 명령어 입력

<br/>
<br/>

- 실습 코드
이미지1,2,3
- 실습 결과
이미지 

---

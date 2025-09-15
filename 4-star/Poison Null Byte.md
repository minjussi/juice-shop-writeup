# Poison Null Byte

### Null Byte Injection




### 문제 풀이

<p align="center">
  <img src="https://github.com/user-attachments/assets/fd3fc1e5-818a-4bcd-a80e-6d2370386587" width="45%" style="margin-right:10px;"/>
  <img src="https://github.com/user-attachments/assets/3eaf6c9d-f223-4e10-b570-c6a07679d9a7" width="45%"/>
</p>

- ftp/package.json.bak%25%30%30.pdf(url encoding)로 null byte를 추가하여 확장자 제한을 우회할 수 있다. 

### Mitigation Strategy

> 문자열 끝에 입력되는 null byte를 처리하는 로직을 따로 두어 null byte injection을 해결

- Allowlist 사용: 입력값에 대한 allowlist를 만들어서 allowlist에 있는 입력값이 아니면 모두 차단한다.

- MIME 타입 사용: 파일 이중 확장자 문제를 해결하기 위해 파일의 MIME 타입을 확인한다.

- 인코딩된 null byte 제거(입력값 sanitize): 사용자 입력값을 그대로 쓰지 않고, 인코딩 된 값을 확인한 후 잘못된 입력값이 있다면 이를 제거하고 파일 경로로 사용한다. 

- string concatenation 하지 않기: node.js에 있는 path.join() 함수 혹은 php에 있는 realpath() 함수를 사용하면 사용자가 입력한 문자열을 검열하지 않고 그대로 합치기 때문에 이를 활용한 우회가 쉬워진다. 따라서 file 경로를 조작하는 안전한 함수를 활용해야 한다.

- parameterized queries 사용하기 (prepared statement): 사용자 입력값과 데이터베이스 명령어를 분리하여 데이터베이스에서 일어날 수 있는 모든 종류의 injection을 방어하는 역할을 한다.
 
> parameterized query(매개변수 쿼리)는 SQL 쿼리 문자열 내에 사용자가 입력한 값을 직접 입력하는 대신, placeholder를 사용하여 SQL 쿼리 자체를 먼저 컴파일 하고, 나중에 해당 placeholder를 실제 값으로 채워 쿼리를 실행하는 동작 방식

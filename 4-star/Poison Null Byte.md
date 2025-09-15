# Poison Null Byte

### Null Byte Injection




### 문제 풀이

<p align="center">
  <img src="https://github.com/user-attachments/assets/fd3fc1e5-818a-4bcd-a80e-6d2370386587" width="45%" style="margin-right:10px;"/>
  <img src="https://github.com/user-attachments/assets/3eaf6c9d-f223-4e10-b570-c6a07679d9a7" width="45%"/>
</p>

- ftp/package.json.bak%25%30%30.pdf(url encoding)로 null byte를 추가하여 확장자 제한을 우회할 수 있다. 

### mitigation

- 문자열 끝에 null byte 

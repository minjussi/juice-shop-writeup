# 🥤Juice Shop Writeups

> 주요 문제 풀이

---

### Reflected XSS (⭐⭐)

URL 파라미터 부분이 reflected xss 공격 지점이라고 판단해서 해당 위치에 인코딩 된 XSS 구문을 삽입

%3Ciframe%20src%3D%22javascript%3Aalert%28%60xss%60%29%22%3E

![image (6)](https://github.com/user-attachments/assets/41a127d5-e3d2-4de5-834b-c5568eab23a3)


---

### Deprecated Interface (⭐⭐)

![image](https://github.com/user-attachments/assets/cc1e4870-b128-48f2-ba04-266d0866474a)
-> XML 파일 업로드를 시도하면 사라진 B2B 인터페이스의 흔적을 찾을 수 있음 (complain 탭에서 업로드 가능)

---

### XXE Data Access (⭐⭐⭐)

XXE(Xml eXternal Entity): 

---

### Poison Null Byte (⭐⭐⭐⭐)

![image](https://github.com/user-attachments/assets/2f1a717e-db98-404e-9506-e747fccc76ce)


![image](https://github.com/user-attachments/assets/3da0742c-f7ba-4737-bf34-0cd9d586c305)

---

### Nested Easter Egg (⭐⭐⭐⭐)

1. null byte injection 시도해서 eastere.gg 파일 다운로드

2. 얻은 파일에 있는 진짜 easter egg 주소를 base 64 인코딩 -> rot 13 인코딩

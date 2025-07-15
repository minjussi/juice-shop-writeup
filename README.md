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

XXE(Xml eXternal Entity) Injection: 외부 객체를 활용해 시스템 파일이나 데이터를 엿볼 수 있는 공격

![image](https://github.com/user-attachments/assets/fd6a1e47-1bbc-471b-89d0-726d382abee3)

-> XXE Injection을 수행하는 XML 파일을 제작해 서버에 전송 (윈도우 환경이기 때문에 /system.ini 에 시스템 파일 존재)

---

### CAPTCHA Bypass (⭐⭐⭐)

<img width="960" height="1135" alt="image" src="https://github.com/user-attachments/assets/184a6a19-d63d-4269-9557-f7bcfa13a681" />

Captcha 우회

---

### CSRF (⭐⭐⭐)


---

### API-only XSS (⭐⭐⭐)

지속적인 XSS 공격 -> Stored XSS의 한 형태이기 때문에 제품 리뷰 작성하는 칸을 활용

<img width="1031" height="915" alt="image" src="https://github.com/user-attachments/assets/56696593-0916-47f4-a010-bee9cef47102" />



---

### Christmas Special (⭐⭐⭐⭐)

<img width="2151" height="1574" alt="image" src="https://github.com/user-attachments/assets/c672880c-13cf-4958-b264-2ef33f5b96ec" />

<img width="2148" height="1243" alt="image" src="https://github.com/user-attachments/assets/8aa5a67b-8bd2-442a-8bd9-8b18c914082c" />


1. burp suite에서 repeater 탭으로 blind sql injection 시도하고, 결과적으로 christmas special offer의 product id가 10임을 알아냄
2. basket에 product id 10을 추가한 다음 checkout

---

### Poison Null Byte (⭐⭐⭐⭐)

![image](https://github.com/user-attachments/assets/2f1a717e-db98-404e-9506-e747fccc76ce)


![image](https://github.com/user-attachments/assets/3da0742c-f7ba-4737-bf34-0cd9d586c305)

---

### Nested Easter Egg (⭐⭐⭐⭐)

1. null byte injection 시도해서 eastere.gg 파일 다운로드

2. 얻은 파일에 있는 진짜 easter egg 주소를 base 64 인코딩 -> rot 13 인코딩

---

### Vulnerable Library (⭐⭐⭐⭐)

- 취약한 라이브러리와 그 버전을 찾는 문제 (앞선 문제에서 얻은 백업 파일 활용)

-> 정답 : express-jwt 0.1.3 

- express-jwt : 

---

### Multiple Likes (⭐⭐⭐⭐⭐⭐)

- Race Condition: 여러 프로세스나 스레드가 공유 자원에 동시에 접근하여 예상치 못한 결과를 초래하는 상황


---

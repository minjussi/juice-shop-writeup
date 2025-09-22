# XXE Data Access

### XXE (XML eXternal Entity) Injection

> XML 데이터란 Extensible Markup Language(확장 가능한 마크업 언어)로, 데이터를 구조화하고 저장하며, 기계와 사람이 모두 읽을 수 있도록 설계된 반정형 데이터 형식이다. HTML과 유사하게 태그를 활용하지만, XML은 데이터 의미와 구조를 정의한다. XML 문서 예시는 다음과 같다. (출처: https://play-with.tistory.com/288)
```XML
<?xml version="1.0" encoding="UTF-8"?>
<book category="fantasy">
  <title>Harry Potter and the Sorcerer's Stone</title>
  <author>J.K. Rowling</author>
  <year>1997</year>
</book>
```

- XML 데이터를 처리할 때 (= parsing) 발생하는 공격으로 주로 공격자가 서버 시스템 파일을 읽을 수 있게 되거나 백엔드 시스템과 상호작용할 수 있게 되는 취약점이다.

### XXE 취약점 발생 & XXE 공격 예시 (출처: PortSwigger)

> 브라우저(client)와 서버(server) 간에 데이터를 주고 받을 때 XML 형식을 사용하는 경우가 있는데, 이때 주로 표준 라이브러리나 API를 사용해 서버 단에 있는 XML 데이터를 처리한다. XML은 잠재적인 위험 요소들이 존재하는데, 대부분의 처리 도구들이 이 요소들을 다루고 있기 때문에 취약점이 발생한다. (cf) DTD(Document Type Definition) 는 XML 문서의 구조, 요소, 속성 등의 규칙을 정의하는 문법이다. )

- 파일을 찾을 때 XXE 활용
  - DOCTYPE 정의: 파일 경로를 포함하는 외부 엔터티 정의
 
```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>  <!--/etc/passwd 파일을 찾는 구문 삽입-->
<stockCheck>
  <productId>&xxe;</productId>                                <!--&xxe 변수에 /etc/passwd 파일 내용이 들어감-->
</stockCheck>
```

- SSRF 공격을 하기 위해 XXE 활용

```XML
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "http://internal.vulnerable-website.com/"> ]>
```

- Content-Type 수정으로 XXE 공격 시도


### 문제 풀이


### Mitigation Strategy


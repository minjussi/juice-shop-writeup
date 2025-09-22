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

- XML 데이터를 처리할 때 발생하는 공격으로 주로 공격자가 서버 시스템 파일을 읽을 수 있게 되거나 백엔드 시스템과 상호작용할 수 있게 되는 취약점이다.

### XXE 취약점 발생 예시



### 문제 풀이


### Mitigation Strategy


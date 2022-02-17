# HICT CMS REST API 정의서

---

## 1. 공통 결과 포멧

- 모든 결과는 JSON 스트링으로 제공됩니다.
- error_code : 6자리 정수로 표현되며, 앞 세자리는 HTTP status code로 뒤 세자리는 세부 정보로 나뉩니다. 에러가 없는 경우에도 반드시 이 필드는 포함됩니다. (ex: 200000)
- result : 결과 값은 result로 제공됩니다.
- 결과 예시
  {"error_msg"."OK"."result"."{\"gender\":\"male\",\"last_name\":\"Kim\"}","error_code":200000}

## 2. 항목

### 2.1 메인 배너 목록 요청

- URL :

  - 프로토콜 :

- request parameter

| Type | Key            | 설명             | 값(예시) |
| ---- | -------------- | ---------------- | -------- |
| text | main_banner_id | 컨텐츠 배너 id   | 100      |
| text | limit          | 가져올 컨텐츠 수 | 20       |

- response

| Key  | 설명           |
| ---- | -------------- |
| {}   | array          |
| seq  | 컨텐츠 배너 id |
| seq1 | 배너 vo 내용   |

- 에러코드

| 코드   | 설명                          |
| ------ | ----------------------------- |
| 500901 | 알수 없는 오류                |
| 500101 | 컨텐츠 배너 id 값이 없습니다. |

### 2.2 소개 페이지에 대한 정보 요청

- URL : /api/{page}

- request parameter

| Type | Key  | 설명      | 값(예시) |
| ---- | ---- | --------- | -------- |
| text | page | 페이지 id | intro    |

```
/api/intro
```

- response

| Key     | 설명 |
| ------- | ---- |
| { }     | JSON |
| TITLE   | 제목 |
| CONTENT | 내용 |

```json
{ "TITLE": "intro", "CONTENT": "<title>행복ICT</title>" }
```

- 에러코드

| 코드   | 설명                          |
| ------ | ----------------------------- |
| 500901 | 알수 없는 오류                |
| 500101 | 컨텐츠 배너 id 값이 없습니다. |

### 2.3 게시판 목록 요청

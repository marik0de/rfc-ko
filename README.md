# rfc-ko

IETF RFC 문서의 한국어 번역입니다. HTTP 의미론(RFC 9110), HTTP/1.1(RFC 9112), HTTP/2(RFC 9113)와 요구 수준 키워드(BCP 14)를 옮겼습니다.

## 번역 목록

| RFC | 제목 | 번역본 | 상태 |
|---|---|---|---|
| [9113](https://www.rfc-editor.org/rfc/rfc9113) | HTTP/2 | [rfc9113.md](translated/rfc9113.md) | 전체 초안 |
| [9112](https://www.rfc-editor.org/rfc/rfc9112) | HTTP/1.1 | [rfc9112.md](translated/rfc9112.md) | 전체 초안. RFC 9931에서 일부 갱신됨 |
| [9110](https://www.rfc-editor.org/rfc/rfc9110) | HTTP Semantics | [rfc9110.md](translated/rfc9110.md) | 전체 번역, 검토 완료 |
| [8174](https://www.rfc-editor.org/rfc/rfc8174) | Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words | [rfc8174.md](translated/rfc8174.md) | BCP 14. 초안 |
| [2119](https://www.rfc-editor.org/rfc/rfc2119) | Key words for use in RFCs to Indicate Requirement Levels | [rfc2119.md](translated/rfc2119.md) | BCP 14, RFC 8174로 갱신됨. 초안 |

초안은 원문 전체를 옮겼지만 아직 검토 중인 번역입니다.

## 폴더 구조

```
rfc-ko/
├── original/             # RFC 원문 (rfc-editor.org에서 받은 그대로)
│   └── SOURCES.md        # 원문 출처와 받은 날짜
├── translated/           # 한국어 번역본
├── glossary.md           # 용어 대역표
└── TRANSLATION_GUIDE.md  # 번역 가이드
```

## 읽는 법

- 번역본 맨 위에 원문 URL, 번역 기준일, 반영한 정오표(errata)가 있습니다. 정오표로 고친 곳은 원문을 취소선으로 남기고 역주를 달았습니다.
- 용어는 처음 나올 때 원어를 함께 씁니다. 예: 흐름 제어(flow control). 전체 대역어는 [용어집](glossary.md)에 있습니다.
- MUST, SHOULD, MAY 같은 규범 키워드는 한국어로 옮기고 괄호 안에 대문자 원어를 남겼습니다. 예: `반드시 ~해야 한다(MUST)`
- `> **역주:**`로 시작하는 인용문은 번역자가 덧붙인 설명입니다.
- 번역 방식은 [번역 가이드](TRANSLATION_GUIDE.md)에 정리했습니다.

## 오류 제보

잘못 옮긴 곳이나 어색한 표현을 발견하면 이슈로 알려 주세요. RFC 번호, 절 번호, 고칠 내용을 함께 적어 주시면 빨리 반영할 수 있습니다.

- 번역자: 김마리 (Mariel Kim), GitHub [@marik0de](https://github.com/marik0de)

## 저작권

RFC 원문의 저작권은 IETF Trust와 각 문서의 저자에게 있습니다. 이 저장소의 번역은 [BCP 78](https://www.rfc-editor.org/info/bcp78)과 [IETF Trust Legal Provisions](https://trustee.ietf.org/documents/trust-legal-provisions/)에 따라 작성되며, 번역본에는 원문의 Copyright Notice를 그대로 유지합니다.

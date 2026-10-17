# 용어 대역표

이 저장소의 모든 RFC 번역에 공통으로 적용하는 용어집입니다. 새 용어는 번역하면서 바로 추가합니다.

## 작성 규칙

- **원어 병기**: `번역어(원어)` 형태로 쓰는 곳은 (1) 요약과 본문에서 각각 처음 나올 때, (2) 원문이 그 용어를 정의하는 곳(예: `The term "origin server" refers to…`처럼 따옴표로 표시된 정의)입니다. 그 밖에는 번역어만 씁니다.
- **원어 유지**: 프레임 유형, 오류 코드, 설정 이름, 메서드, 헤더 이름, ABNF 규칙 이름, 스트림 상태 이름 등 프로토콜 식별자는 번역하지 않습니다. 예: `GOAWAY`, `PROTOCOL_ERROR`, `GET`, `half-closed (로컬)`
- **출처 열**: 그 용어를 처음 정의하거나 주로 다루는 RFC입니다. 여러 RFC에서 쓰면 `공통`으로 적습니다.
- **같은 원어, 다른 의미**: RFC마다 뜻이 달라지는 용어는 한 행에 몰지 말고 비고에 RFC별 의미를 적습니다.
- **변경 시**: 이미 번역한 문서에 쓴 용어를 바꾸면 해당 번역본도 함께 고칩니다.

## 규범 키워드 (RFC 2119, RFC 8174)

대문자로 쓴 키워드는 한국어로 옮기고, 문장 끝 괄호 안에 대문자 원어를 남깁니다. 예: `반드시 ~해야 한다(MUST)`

RFC 2119에서 같은 단계로 묶인 키워드(예: SHOULD와 RECOMMENDED)는 **강도가 같습니다.** 이 저장소에서는 강도는 그대로 두고, 품사와 쓰임에 맞게 한국어 표현만 나눕니다. RECOMMENDED는 권고 사항으로 옮깁니다.

| 원어 | 번역 표현 | 비고 |
|---|---|---|
| MUST | 반드시 ~해야 한다(MUST) | 절대적 요구 사항 |
| REQUIRED | 필수다(REQUIRED) / 반드시 ~해야 한다(REQUIRED) | 형용사. MUST와 같은 강도 |
| SHALL | 반드시 ~해야 한다(SHALL) | MUST와 같은 강도 |
| MUST NOT | ~해서는 안 된다(MUST NOT) | 절대적 금지 |
| SHALL NOT | ~해서는 안 된다(SHALL NOT) | MUST NOT과 같은 강도 |
| SHOULD | ~해야 한다(SHOULD) | 타당한 이유가 있으면 예외 가능 |
| RECOMMENDED | ~할 것을 권고한다(RECOMMENDED) | 권고 사항. 형용사. SHOULD와 같은 강도 |
| SHOULD NOT | ~하지 않아야 한다(SHOULD NOT) | 타당한 이유가 있으면 예외 가능 |
| NOT RECOMMENDED | ~하지 않을 것을 권고한다(NOT RECOMMENDED) | 형용사. SHOULD NOT과 같은 강도 |
| MAY | ~할 수 있다(MAY) | 선택 사항 |
| OPTIONAL | 선택 사항이다(OPTIONAL) | 형용사. MAY와 같은 강도 |

소문자 must, should, may는 규범 키워드가 아니므로 일반 서술로 번역합니다.

### BCP 14 고정 문구

대부분의 RFC가 앞부분(용어 절)에 넣는 문구입니다. 번역할 때 아래 번역을 그대로 씁니다. 출처는 RFC 8174 번역 2절입니다.

> 원문: The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [RFC2119] [RFC8174] when, and only when, they appear in all capitals, as shown here.
>
> 번역: 이 문서의 키워드 "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", "OPTIONAL"은 여기에 보인 것처럼 모두 대문자로 쓰였을 때, 그리고 그때에만 BCP 14 [RFC2119] [RFC8174]에 설명된 대로 해석한다.

RFC 8174 이전 문서처럼 문구가 다르면(예: "described in RFC 2119"로 끝나는 옛 문구) 위 번역을 바탕으로 원문에 맞게 고칩니다.

### 번역 예시

예시 문장은 RFC 9113에서 가져왔고, RECOMMENDED와 OPTIONAL만 RFC 9110에서 가져왔습니다.

| 키워드 | 원문 | 번역 |
|---|---|---|
| MUST | Clients and servers MUST treat an invalid connection preface as a connection error (Section 5.4.1) of type PROTOCOL_ERROR. | 클라이언트와 서버는 유효하지 않은 연결 프리페이스를 반드시 `PROTOCOL_ERROR` 유형의 연결 오류(5.4.1절)로 처리해야 한다(MUST). |
| MUST (수동태) | The SETTINGS frames received from a peer as part of the connection preface MUST be acknowledged (see Section 6.5.3) after sending the connection preface. | 엔드포인트는 연결 프리페이스의 일부로 피어에게서 받은 `SETTINGS` 프레임에, 자신의 연결 프리페이스를 보낸 뒤 반드시 확인 응답을 보내야 한다(MUST)(6.5.3절 참조). |
| MUST NOT | Endpoints MUST NOT exceed the limit set by their peer. | 엔드포인트는 피어가 설정한 한도를 초과해서는 안 된다(MUST NOT). |
| SHOULD | Endpoints SHOULD send a GOAWAY frame when ending a connection, providing that circumstances permit it. | 엔드포인트는 상황이 허락한다면 연결을 끝낼 때 `GOAWAY` 프레임을 보내야 한다(SHOULD). |
| SHOULD NOT | Endpoints SHOULD NOT use timers for this purpose. | 엔드포인트는 이 목적으로 타이머를 사용하지 않아야 한다(SHOULD NOT). |
| RECOMMENDED (RFC 9110) | It is RECOMMENDED that all senders and recipients support, at a minimum, URIs with lengths of 8000 octets in protocol elements. | 모든 송신자와 수신자는 프로토콜 요소에서 최소 8000옥텟 길이의 URI를 지원할 것을 권고한다(RECOMMENDED). |
| MAY | An endpoint MAY choose to treat a stream error as a connection error. | 엔드포인트는 스트림 오류를 연결 오류로 처리할 수 있다(MAY). |
| OPTIONAL (RFC 9110) | All other methods are OPTIONAL. | 그 밖의 모든 메서드는 선택 사항이다(OPTIONAL). |
| (키워드 아님) | An endpoint can end a connection at any time. | 엔드포인트는 언제든지 연결을 끝낼 수 있다. |

수동태 MUST는 능동태로 바꾸고, 원문에 없는 주어는 문맥상 분명할 때만 보충합니다. 위 예시에서 "엔드포인트는"은 역자가 보충한 주어입니다. 해석이 갈리면 역주로 남깁니다.

마지막 예시의 can은 규범 키워드가 아니므로 MAY와 달리 괄호를 붙이지 않습니다.

## 표기 예시

| 대상 | 원문 | 번역 | 규칙 |
|---|---|---|---|
| 원어 병기 | The initial value for the flow-control window is 65,535 octets ... | 흐름 제어 윈도우(flow-control window)의 초기값은 ... 65,535옥텟이다. | 문서에서 처음 나올 때만 병기 |
| 절 참조 | (Section 5.4.1) | (5.4.1절) | 다른 RFC는 `RFC 9110의 8.6절` |
| 식별자 | a frame of type PROTOCOL_ERROR | `PROTOCOL_ERROR` 유형의 프레임 | 번역하지 않고 코드 서식 |
| 숫자 | 65,535 octets | 65,535옥텟 | 쉼표 자릿수 구분 유지 |

## 공통 · HTTP 의미론

| 원어 | 번역어 | 비고 | 출처 |
|---|---|---|---|
| absolute URI | 절대 URI | 스킴부터 전체 경로를 모두 기술한 URI 표현(상대 URI와 대비). RFC 3986의 `absolute-URI` 규칙은 프래그먼트를 포함하지 않음. 정보통신기술용어해설: 절대 URI | RFC 9110 |
| abstract data type | 추상 데이터형 | TTA: 추상 데이터형. 정보통신기술용어해설: 추상 자료형, 추상 데이터 타입, 추상 데이터형 | 공통 |
| accelerator | 가속기 | 예: 가속기 캐싱 | RFC 9110 |
| access control | 접근 제어 | TTA: 접근 제어 | 공통 |
| active content | 능동 콘텐츠 | 사용자 에이전트 특성에 따라 추가 요청을 하는 스크립트가 든 표현(12장) | RFC 9110 |
| ad hoc | 임시방편 | "in an ad hoc fashion"은 임시방편으로(16.3.2절) | 공통 |
| administrative domain | 관리 도메인 | | 공통 |
| agent-driven negotiation | 에이전트 주도 협상 | reactive negotiation의 다른 이름(12.2절) | RFC 9110 |
| alias | 별칭 | 관용 표기(번역자 결정). TTA: 별명. 정보통신기술용어해설: 별칭, 앨리어스 | 공통 |
| alternative service | 대체 서비스 | [ALTSVC](RFC 7838)의 서비스(15.5.20절) | RFC 9110 |
| analytics | 분석 | 예: 간단한 분석, 브라우저 사용 분석 | 공통 |
| annotation | 주석 | 예: 주석 서비스 | RFC 9110 |
| anonymization | 익명화 | TTA: 익명화. 정보통신기술용어해설: 해당 항목 없음 | 공통 |
| application | 애플리케이션 | "application-specific"은 애플리케이션별. 15~17장에 섞여 있던 "응용"을 전수 검사에서 통일 | 공통 |
| application-level | 애플리케이션 수준 | 예: 애플리케이션 수준 프로토콜 | RFC 9110 |
| asynchronous | 비동기 | TTA·정보통신기술용어해설 같음 | 공통 |
| atomic | 원자적 | "nonatomic increment"는 원자적이지 않은 증가(13.1.1절). TTA: 원자. 정보통신기술용어해설: 해당 항목 없음(화학 원자만) | 공통 |
| audit log | 감사 로그 | | RFC 9110 |
| authenticated encryption | 인증된 암호화 | 정보통신기술용어해설: 없음. TTA 표준: 인증된 암호화(11.3절) | 공통 |
| authentication | 인증 | TTA·정보통신기술용어해설: 인증 | 공통 |
| authentication parameter | 인증 매개 변수 | ABNF 규칙 이름 `auth-param`은 원어 | RFC 9110 |
| authentication scheme | 인증 스킴 | 예: "basic", "digest"(스킴 이름은 원어). ABNF 규칙 이름 `auth-scheme`은 원어 | RFC 9110 |
| authenticity | 진정성 | 주소 매핑의 진정성(17.1절) | 공통 |
| authoring | 저작 | 예: 저작 애플리케이션, 저작 도구 | 공통 |
| authoritative | 권한 있는 | 예: 권한 있는 응답. 권한(authority)에서 나온다는 뜻(Merriam-Webster) | RFC 9110 |
| authoritative access | 권한 있는 접근 | 리소스 소유자가 통제한다고 믿는 방식으로 식별자를 역참조해 접근하는 것(4.3절) | RFC 9110 |
| authority | 권한 | "authoritative response"는 권한 있는 응답, "establishing authority"는 권한 확립(권한을 확립하는 과정, 17.1절). URI 구성 요소는 authority component 행 참고 | 공통 |
| authority component | authority 구성 요소 | URI 구성 요소 이름([URI]의 3.2절)이라 원어 유지. 직역하면 "권한 구성 요소". 4.2.1절에 역주 | 공통 |
| authorization | 인가 | 헤더 필드 이름 `Authorization`은 원어. TTA: 인가. 정보통신기술용어해설: 인가, 권한 부여 | 공통 |
| availability | 가용성 | 관용 표기(번역자 결정). TTA: 이용도. 정보통신기술용어해설: 가용성 | 공통 |
| back link | 역링크 | 원래 표현의 원천으로 돌아가는 링크(8.7절) | 공통 |
| backup | 백업 | TTA·정보통신기술용어해설 같음 | 공통 |
| bare CR | 단독 CR | 번역자 결정(제안 표기 확정. 사전에 없음). 바로 뒤에 LF가 오지 않는 CR(2.2절) | RFC 9112 |
| base64 | base64 | 인코딩 이름이라 원어(base64url, base32, base16도 같음). TTA: 베이스 64 | 공통 |
| batch processing | 일괄 처리 | "batch-oriented process"는 일괄 처리(15.3.3절). TTA 같음. 정보통신기술용어해설: Batch Processing(다중 처리 항목 안) | 공통 |
| blind relay | 맹목적 중계 | 메시지를 해석하거나 바꾸지 않고 그대로 넘김. blind의 "분별 없이"라는 뜻(Merriam-Webster) | RFC 9110 |
| body part | 본문 부분 | 멀티파트 메시지 본문의 각 부분(14.6절) | RFC 9110 |
| boundary | 경계 | 멀티파트의 `boundary` 매개 변수(이름은 원어) | 공통 |
| browsing history | 탐색 기록 | | 공통 |
| buffer | 버퍼 | 동사로는 "버퍼에 담다". TTA·정보통신기술용어해설: 버퍼 | 공통 |
| byte range | 바이트 범위 | "bytes" 범위 단위로 지정한 범위(14.1.2절) | RFC 9110 |
| cache | 캐시 | | RFC 9110 |
| cache directive | 캐시 지시자 | 예: `no-transform` 캐시 지시자. 지시자 이름은 원어. TTA: 없음 | RFC 9110 |
| cache entry | 캐시 항목 | | RFC 9110 |
| cache key | 캐시 키 | | RFC 9110 |
| cache poisoning | 캐시 중독 | 동사로는 "캐시를 중독시키다". TTA: 캐시 중독 | 공통 |
| cacheable | 캐시 가능한 | | RFC 9110 |
| canonical | 정규형(의) | "not canonical"은 정규형이 아닌(14.1.2절). TTA: 정규(정규 함수 등). 정보통신기술용어해설: 표준형(제어 공학) | 공통 |
| cardinality | 원소 개수 | 목록 요소의 개수 제약(5.6.1.2절). TTA: 사상수(TTA 표준). 정보통신기술용어해설: 집합 크기, 원소의 개수, 카디널리티 | 공통 |
| certificate | 인증서 | | 공통 |
| chain of trust | 신뢰 체인 | 신뢰 앵커에서 이어지는 인증서 사슬 | 공통 |
| challenge | 챌린지 | 관용 표기(번역자 결정). 서버가 인증을 요구하며 보내는 값(11.3절). TTA: 식별 신청(-응답 절차). 정보통신기술용어해설: 챌린지, 시도 응답 인증. 동사 "challenge the authorization"은 "인가를 요구하다". ABNF 규칙 이름 `challenge`는 원어 | 공통 |
| challenge-response | 챌린지-응답 | 관용 표기(번역자 결정). TTA: 식별 신청-응답 절차. 정보통신기술용어해설: 챌린지, 시도 응답 인증, 챌린지 리스펀스 | 공통 |
| change controller | 변경 관리자 | IANA 등록 항목(14.6·18장) | 공통 |
| charset | charset | 원어 유지. 문자 인코딩 스킴의 이름(8.3.2절, [RFC6365]). "문자 집합"으로 옮기면 character set과 혼동되므로 쓰지 않음 | 공통 |
| checksum | 체크섬 | 관용 표기(번역자 결정). TTA: 검사합. 정보통신기술용어해설: 체크섬, 검사합 | 공통 |
| chunk | 청크 | 청크 전송 코딩의 데이터 조각 | RFC 9110 |
| chunk extension | 청크 확장 | 청크마다 붙이는 확장(7.1.1절). ABNF 규칙 이름 `chunk-ext`는 원어 | RFC 9112 |
| chunked transfer coding | 청크 전송 코딩 | HTTP/1.1 전송 코딩의 하나. 코딩 이름 `chunked`는 원어 | RFC 9110 |
| class (status code) | 클래스 | 상태 코드 첫 자리가 정하는 분류(15장). 클래스 이름은 `2xx (Successful)`처럼 원어 | RFC 9110 |
| client | 클라이언트 | | 공통 |
| clock | 시계 | UTC 현재 시점을 근사해 제공하는 구현(5.6.7절) | RFC 9110 |
| clock resolution | 시계 해상도 | | 공통 |
| closure alert | 종료 경고 | 번역자 결정(제안 표기 확정. 두 사전 모두 해당 항목 없음). TLS 종료 경고(9.8절) | RFC 9112 |
| coalesce | 병합하다 | 겹치거나 가까운 범위를 합침(15.3.7.2절) | RFC 9110 |
| collision-resistant hash | 충돌 저항 해시 | 예: 충돌 저항 해시 함수 | 공통 |
| combined field value | 결합된 필드 값 | 같은 이름의 필드 줄 값을 쉼표로 이어 붙인 값(5.2절) | RFC 9110 |
| comment | 주석 | 괄호로 감싼 필드 주석(5.6.5절). ABNF 규칙 이름 `comment`는 원어. annotation(주석)과 번역어가 같으니 문맥으로 구분. TTA: 주석란(comment field) | 공통 |
| complete (message) | 완전한 (메시지) | 프레이밍이 나타내는 모든 옥텟을 사용할 수 있는 상태(6.1절) | RFC 9110 |
| conditional content | 조건부 콘텐츠 | 사용자 에이전트 매개 변수에 따라 부분을 골라 렌더링하는 표현(12장) | RFC 9110 |
| conditional request | 조건부 요청 | | RFC 9110 |
| confidentiality | 기밀성 | TTA·정보통신기술용어해설 같음. "confidential"은 기밀(의) | 공통 |
| conformance, conformant | 적합성, 적합한 | 예: 적합성 기준, 적합한 구현. conformant는 문맥에 따라 "적합한", "준수하는", "지원하는/호환되는" 중에서 고른다. 버전에 대해 쓰일 때(conformant to a version)는 "지원하는"(2.5·6.2절) | RFC 9110 |
| congestion | 혼잡 | 정보통신기술용어해설: 혼잡. TTA: 정체 현상 | 공통 |
| connection | 연결 | | 공통 |
| connection option | 연결 옵션 | `Connection` 헤더 필드에 나열하는 옵션(7.6.1절). ABNF 규칙 이름 `connection-option`은 원어 | RFC 9110 |
| container | 컨테이너 | TTA·정보통신기술용어해설 같음. "message/http" 컨테이너(5.2절) | 공통 |
| content | 콘텐츠 | RFC 9110에서 payload를 대체한 용어 | RFC 9110 |
| content coding | 콘텐츠 코딩 | 예: gzip | RFC 9110 |
| content delivery network (CDN) | 콘텐츠 전송망 | TTA: 콘텐츠 전송망 | RFC 9110 |
| content negotiation | 콘텐츠 협상 | | RFC 9110 |
| control data | 제어 데이터 | 요청의 메서드·요청 대상·버전, 응답의 상태 코드·이유 구문·버전(6.2절) | RFC 9110 |
| credential | 자격 증명 | 관용 표기(번역자 결정). 5.3절 "인증 자격 증명"과 같음. TTA·정보통신기술용어해설: 크리덴셜 | 공통 |
| cross-site request forgery (CSRF) | 사이트 간 요청 위조 | 관용 표기(번역자 결정). OWASP·MDN 한국어 표기. TTA: 크로스 사이트 리퀘스트 변조 | 공통 |
| cyclic redundancy check (CRC) | 순환 중복 검사 | 관용 표기(번역자 결정). TTA: 주기적 덧붙임 검사. 정보통신기술용어해설: 순환 중복 검사 | 공통 |
| deep linking | 딥 링킹 | TTA: 딥 링크(deeplink) | 공통 |
| delimited (close-/length-/chunk-delimited) | (연결 종료/길이/청크)로 끝이 구분되는 | 예: close-delimited 연결 종료로 끝이 구분되는(6.3절), length-delimited 길이로 끝이 구분되는(7.1절). delimiter(구분자) 참고 | RFC 9112 |
| delimiter | 구분자 | 문자든 길이 정보든 경계를 표시하는 것 모두(예: "@" 구분자, 길이 기반 데이터 구분자). separator도 "구분자"로 옮기므로 구별이 필요하면 원어 병기. TTA: 구분 문자 | 공통 |
| denial of service | 서비스 거부 | TTA: 서비스 거부(분산형 서비스 거부 공격) | 공통 |
| deprecated | 사용 중단 | 예: "user:password" 형식은 사용이 중단되었다. TTA: 없음 | 공통 |
| dereference | 역참조 | 식별자를 따라가 대상에 접근하는 것. Merriam-Webster: 항목 없음 | RFC 9110 |
| designated expert | 지정 전문가 | IANA 등록을 심사하는 전문가(16.3.1절, RFC 8126) | 공통 |
| digest | 다이제스트 | TTA·정보통신기술용어해설: 메시지 다이제스트 | 공통 |
| digital signature | 전자 서명 | TTA: 전자 서명. 정보통신기술용어해설: 전자 서명, 디지털 서명 | 공통 |
| distributed object | 분산 객체 | TTA: 분산 객체(분산 객체 관리 기능) | 공통 |
| document view | 문서 보기 | 사용자 에이전트가 보여 주는 현재 문서 화면(15.3.5·15.3.6절) | RFC 9110 |
| downgrade | 다운그레이드 | 번역자 결정(제안 표기 확정. 두 사전 모두 해당 항목 없음) | 공통 |
| downstream / upstream | 다운스트림 / 업스트림 | 메시지가 흘러가는 방향. TTA: 하향 스트림 / 상향 스트림 | RFC 9110 |
| effective request URI | 유효 요청 URI | 이전 명세에서 재구성된 대상 URI를 부르던 이름(7.1절) | RFC 9110 |
| empty line | 빈 줄 | 헤더 섹션 끝을 나타내는 CRLF(2.1절) | RFC 9112 |
| end-to-end | 종단 간 | | 공통 |
| endpoint | 엔드포인트 | | 공통 |
| entity tag | 엔터티 태그 | `ETag` 헤더 필드의 값(8.8.3절). TTA: 없음. 정보통신기술용어해설: entity → 엔티티, 엔터티 | RFC 9110 |
| environment variable | 환경 변수 | 정보통신기술용어해설: 환경 변수 | 공통 |
| establishing authority | 권한 확립 | 17.1절 제목. 권한 있는 응답(authoritative response)을 판단하는 일 | RFC 9110 |
| expectation | 기대 | `Expect` 헤더 필드의 구성원(10.1.1절). 예: 100-continue 기대 | RFC 9110 |
| explicit / implicit framing | 명시적 / 암묵적 프레이밍 | 암묵적 프레이밍은 연결을 닫아 메시지 끝을 알리는 방식(6.1절) | RFC 9110 |
| exploit | 악용하다 | 동사. 정보통신기술용어해설: 익스플로잇, 취약점 공격(명사) | 공통 |
| extensibility | 확장성 | 16장 절 제목(메서드 확장성 등) | 공통 |
| extension point | 확장 지점 | 새 버전 없이 기능을 더할 수 있는 지점(16장) | RFC 9110 |
| federated namespace | 연합 네임스페이스 | 위임된 등록 이름과 IP 주소로 이루어진 네임스페이스 | RFC 9110 |
| field | 필드 | 헤더와 트레일러를 아우르는 말 | RFC 9110 |
| field line | 필드 줄 | 필드 이름과 필드 줄 값으로 이루어진 한 줄(5.2절) | RFC 9110 |
| field line value | 필드 줄 값 | | RFC 9110 |
| field name | 필드 이름 | | RFC 9110 |
| field value | 필드 값 | | RFC 9110 |
| file system | 파일 시스템 | 정보통신기술용어해설: 파일 시스템 | 공통 |
| final response | 최종 응답 | 중간 응답(interim response)이 아닌 응답(15장) | RFC 9110 |
| fingerprinting | 핑거프린팅 | 관용 표기(번역자 결정). 사용자를 원치 않게 식별하는 것. TTA: 디지털 지문. 정보통신기술용어해설: 핑거프린트 | 공통 |
| firewall | 방화벽 | TTA·정보통신기술용어해설: 방화벽 | 공통 |
| FQDN | FQDN | fully qualified domain name, 정규화된 도메인 이름. 본문 첫 등장(7.7절)에 원어와 뜻을 함께 적음 | 공통 |
| fragment identifier | 프래그먼트 식별자 | URI의 `#` 뒤 부분. TTA: 프래그먼트 식별 기호(TTA 표준) | 공통 |
| framework | 프레임워크 | TTA·정보통신기술용어해설 같음 | 공통 |
| freshness | 신선도 | 캐시 응답이 아직 쓸 만한 정도. TTA: 표제어 없음(다른 항목 해설에 "최신성") | RFC 9110 |
| fully qualified domain name (FQDN) | 전체 주소 도메인 이름 | TTA: 전체 주소 도메인 이름 | 공통 |
| gateway | 게이트웨이 | | RFC 9110 |
| generate | 생성하다 | "보내다(send)"와 구분. 요소를 직접 만드는 경우에만 씀 | RFC 9110 |
| generic interface | 범용 인터페이스 | TTA: generic → 범용(예: 범용 정보 보호 서비스 API) | RFC 9110 |
| graceful close | 우아한 종료 | 번역자 결정(표기 유지). 정상 종료를 뜻함. 두 사전 모두 해당 항목 없음(TTA의 graceful exit는 우아한 종료)(9.5절) | RFC 9112 |
| half-close | 하프 클로즈 | 번역자 결정(표기 유지). 반연결 해제: 연결을 완전히 끊기 전에 송신 쪽만 닫고 수신은 유지하는 것(9.6절). 두 사전 모두 해당 항목 없음 | RFC 9112 |
| handler routine | 처리 루틴 | | 공통 |
| handshake | 핸드셰이크 | 번역자 결정(제안 표기 확정). 정보통신기술용어해설: 핸드세이크, 핸드세이킹, 핸드쉐이크. TTA: 핸드셰이크, 핸드세이크 혼용 | 공통 |
| hard-coded | 하드코딩된 | | 공통 |
| hash function | 해시 함수 | TTA·정보통신기술용어해설: 해시 함수 | 공통 |
| hash table | 해시 테이블 | 정보통신기술용어해설: 해시 테이블. TTA: 해시표 | 공통 |
| head-of-line blocking | HOL 블로킹 | 번역자 결정. HoLB라고도 함. 두 사전 모두 해당 항목 없음(9.4절) | 공통 |
| header block | 헤더 블록 | HTTP/2·HTTP/3에서 필드를 담는 블록 | RFC 9110 |
| header field | 헤더 필드 | | RFC 9110 |
| header section / trailer section | 헤더 섹션 / 트레일러 섹션 | | RFC 9110 |
| heuristic | 휴리스틱 | 관용 표기(번역자 결정). "heuristically cacheable"은 휴리스틱 캐시 가능, "heuristic expiration"은 휴리스틱 만료(15.1절). TTA: 발견적(발견적 탐색 등). 정보통신기술용어해설: 휴리스틱 | 공통 |
| hop-by-hop | 홉 단위 | | 공통 |
| Huffman coding | 허프만 부호화 | TTA: MH 부호화 방식(modified Huffman). 정보통신기술용어해설: 허프만 부호화 등 | 공통 |
| idempotent | 멱등 | 예: 멱등 메서드. TTA: 등멱원(TTAS.KO-10.0179 웹서비스 용어) | RFC 9110 |
| idle (client) | 유휴 | "idle client"는 유휴 클라이언트(17.16.2절). HTTP/2 스트림 상태 `idle`은 원어 | 공통 |
| impersonation | 위장 | 예: 서버 위장. TTA: 위장(masquerade, impersonation) | 공통 |
| implementation | 구현 | | 공통 |
| in band / out of band | 대역 내 / 대역 외 | 예: 대역 내에서든 대역 외에서든. TTA: 대역 외(대역 외 신호) | 공통 |
| inbound / outbound | 인바운드 / 아웃바운드 | 요청 경로 기준. 인바운드는 원본 서버 쪽, 아웃바운드는 사용자 에이전트 쪽. TTA: 인바운드 / 아웃바운드 | RFC 9110 |
| inclusive | 양 끝 포함 | 바이트 위치가 범위의 양 끝을 포함함(14.1.2절) | 공통 |
| incomplete close | 불완전한 종료 | TLS에서 상대의 종료 경고를 기다리지 않고 연결을 닫는 것(9.8절). complete (message)의 "완전한"과 짝 | RFC 9112 |
| information hiding | 정보 은닉 | TTA: 정보 은닉(TTA 표준), 정보 감춤(용어사전) | RFC 9110 |
| informational response | 정보 응답 | `1xx` 응답(9.2절). interim response(중간 응답)와 같은 대상 | RFC 9112 |
| informative references | 참고용 참고 문헌 | RFC 9110 19.2절 제목 | 공통 |
| injection | 인젝션 | "SQL injection"은 SQL 인젝션(17.4절). 정보통신기술용어해설 표기. TTA: (SQL) 주입 공격 | 공통 |
| integrity check | 무결성 검사 | 예: 메시지 무결성 검사. 정보통신기술용어해설: 메시지 무결성 코드(MIC) 등 | 공통 |
| interception proxy | 가로채기 프록시 | 클라이언트가 선택하지 않은 프록시. "투명 프록시"라고도 함 | RFC 9110 |
| interim response | 중간 응답 | 1xx 응답. non-interim response(중간 응답이 아닌 응답)와 짝 | RFC 9110 |
| intermediary | 중개자 | 프록시, 게이트웨이, 터널을 통칭 | RFC 9110 |
| intermediation | 중개 | | RFC 9110 |
| interpreter | 인터프리터 | 정보통신기술용어해설: 인터프리터 | 공통 |
| language range | 언어 범위 | `Accept-Language`의 `language-range`([RFC4647] 2.1절). ABNF 규칙 이름은 원어 | RFC 9110 |
| language tag | 언어 태그 | RFC 5646의 언어 태그. ABNF 규칙 이름 `language-tag`은 원어 | 공통 |
| latency | 지연 시간 | TTA: 지연(초저지연 등). 정보통신기술용어해설: 지연, 레이턴시 | 공통 |
| leap second | 윤초 | TTA: 윤초 | 공통 |
| legacy | 레거시 | 관용 표기(3장부터 사용). TTA: 기존(기존 시스템 등). 정보통신기술용어해설: 레거시(구형, 기존의) | 공통 |
| lenient parsing | 관대한 파싱 | 규칙보다 너그럽게 받아들이는 파싱(3장) | RFC 9112 |
| line break | 줄바꿈 | 번역자 결정. 문장이나 문단의 끝을 나타내는 실제 구분자(부록 B.2). line folding(자동 줄바꿈), line terminator(개행 문자)와 구분 | RFC 9112 |
| line folding | 자동 줄바꿈 | 번역자 결정. 시스템 제약이나 가독성을 위해 긴 줄을 나누는 기법으로, 실제 줄 구분자인 line break(줄바꿈)와 구분. "obsolete line folding"은 폐기된 자동 줄바꿈(5.2절), ABNF 규칙 이름 `obs-fold`는 원어. 두 사전 모두 해당 항목 없음 | RFC 9112 |
| line terminator | 개행 문자 | 번역자 결정. 줄을 끝낼 때 쓰는 문자(end of line). 두 사전 모두 해당 항목 없음(정보통신기술용어해설은 Line Termination을 "라인 종료")(2.2절) | 공통 |
| line-ending | 줄 끝 | 2.2절 | RFC 9112 |
| link-editing | 링크 편집 | 참조를 고치는 기능(15.4.2절) | RFC 9110 |
| list-based field | 목록 기반 필드 | 여러 구성원을 허용하는 필드(5.5절) | RFC 9110 |
| load balancing | 부하 분산 | TTA: 부하 분산 | RFC 9110 |
| locale | 로케일 | TTA·정보통신기술용어해설 같음(정보통신기술용어해설은 "지역 매개변수"도 함께 실음) | 공통 |
| long polling | 롱 폴링 | 번역자 결정(제안 표기 확정. 두 사전 모두 해당 항목 없음. 7.1.1절) | RFC 9112 |
| lookup table | 조회 테이블 | 이름/값 쌍의 표(6장). TTA: table lookup → 표 찾아보기(과정). 정보통신기술용어해설: 룩업(조회) | 공통 |
| loop-back | 루프백 | 관용 표기(번역자 결정). TTA: 되돌림. 정보통신기술용어해설: 루프백 | 공통 |
| lost update | 갱신 손실 | 다른 클라이언트의 변경을 덮어써 잃는 문제(8.8절) | 공통 |
| magic number | 매직 넘버 | 미디어 유형 등록 양식 항목(14.6절). 두 사전 모두 해당 항목 없음 | 공통 |
| major version / minor version | 주 버전 / 부 버전 | | RFC 9110 |
| malware | 악성 소프트웨어 | TTA: 악성 소프트웨어. 정보통신기술용어해설: 악성 코드, 멀웨어 | 공통 |
| media range | 미디어 범위 | `Accept`의 `media-range`(12.5.1절). 예: `text/*`, `*/*`. ABNF 규칙 이름은 원어 | RFC 9110 |
| media type | 미디어 유형 | 관용 표기(번역자 결정). 상태 코드 이름(예: `415 (Unsupported Media Type)`)은 원어. TTA: 매체 형식 | 공통 |
| message | 메시지 | | 공통 |
| message authentication code | 메시지 인증 코드 | TTA·정보통신기술용어해설 같음. MAC | 공통 |
| message body | 메시지 본문 | HTTP/1.1에서 프레이밍된 본문. 콘텐츠와 구분(6.4절). 정보통신기술용어해설: 메시지 | RFC 9110 |
| message framing | 메시지 프레이밍 | 메시지의 경계를 정하는 것. 정보통신기술용어해설: 프레이밍 | RFC 9110 |
| messaging syntax | 메시지 구문 | 버전별 와이어 포맷. 의미론과 구분 | RFC 9110 |
| meta-variable | 메타 변수 | CGI의 메타 변수(17.10절, RFC 3875) | 공통 |
| method | 메서드 | | RFC 9110 |
| method-preserving | 메서드를 유지하는 | 리다이렉트할 때 요청 메서드를 바꾸지 않음(15.4절) | RFC 9110 |
| MIME sniffing | MIME 스니핑 | 콘텐츠를 살펴 미디어 유형을 추측하는 것. TTA: 스니핑 | 공통 |
| mint | (식별자를) 만들다 | 예: URI를 만들다. Merriam-Webster: create, produce | RFC 9110 |
| misdirected request | 잘못 전달된 요청 | `421 (Misdirected Request)` | RFC 9110 |
| mitigation | 완화 | "mitigation strategy"는 완화 전략. 두 사전 모두 해당 항목 없음 | 공통 |
| modification date | 수정 일자 | `Last-Modified`가 나타내는 날짜(13.1.3절) | RFC 9110 |
| modifier | 수정자 | 다른 것의 해석을 바꾸는 것. 예: `Content-Encoding`은 미디어 유형에 대한 수정자(RFC 9112 부록 B.4). request modifier(요청 수정자) 참고 | 공통 |
| multi-tenant | 멀티테넌트 | 여러 사용자(테넌트)가 한 서버를 나눠 쓰는 배포(16.3.2절). 두 사전 모두 해당 항목 없음 | 공통 |
| multibyte | 멀티바이트 | 번역자 결정(제안 표기 확정. 두 사전 모두 해당 항목 없음) | 공통 |
| multihomed | 멀티 홈드 | 정보통신기술용어해설: 멀티 호밍, 멀티 홈드, 다중 호밍. TTA: 없음(부록 C.2.1) | 공통 |
| multipart | 멀티파트 | 예: 멀티파트 메시지 본문. TTA·정보통신기술용어해설: 해당 항목 없음 | 공통 |
| name resolution | 이름 해석 | 등록된 이름을 IP 주소로 바꾸는 것(예: DNS). TTA: 이름 분석 | 공통 |
| name-based virtual host | 이름 기반 가상 호스트 | TTA: 가상 호스트(이름 기반 가상 호스트). 정보통신기술용어해설: 없음(부록 C.1) | 공통 |
| namespace | 네임스페이스 | TTA: 네임스페이스 | 공통 |
| natural language | 자연어 | TTA·정보통신기술용어해설: 자연어 | 공통 |
| negotiation | 협상 | 관용 표기(번역자 결정). TTA: 교섭. 정보통신기술용어해설: 협상(BGP 이웃 협상), 자동 절충 | 공통 |
| network effect | 네트워크 효과 | | 공통 |
| non-interim response | 중간 응답이 아닌 응답 | 1xx가 아닌 최종 응답(15장) | RFC 9110 |
| normalization | 정규화 | 예: 구문 기반 정규화, 스킴 기반 정규화. TTA: 정규화 | 공통 |
| normative references | 규범 참고 문헌 | RFC 8174 5장, RFC 9110 19.1절 제목 | 공통 |
| obfuscate | 가리다 | "userinfo obfuscating the authority component"는 authority 구성 요소를 가리는 `userinfo`(17.1절). TTA: 난독화(코드 난독화) | 공통 |
| octet | 옥텟 | 8비트. "바이트"로 바꾸지 않음 | 공통 |
| offset | 오프셋 | TTA: 오프셋. 정보통신기술용어해설: 옵셋, 오프셋 | 공통 |
| on-path attacker | 경로상 공격자 | 통신 경로 위에 있는 공격자 | RFC 9110 |
| opaque data | 불투명한 데이터 | 내용을 해석하지 않고 그대로 다루는 데이터 | 공통 |
| optimistic concurrent writes | 낙관적 동시 쓰기 | 17.14절 | 공통 |
| origin | 출처 | 스킴·호스트·포트 세 값의 묶음(4.3.1절). MDN 한국어 등 웹 보안 문서의 "동일 출처 정책"과 맞춤. source를 옮길 때는 출처를 쓰지 않음(예: untrusted source → 신뢰할 수 없는 곳). TTA: 웹 origin 항목 없음 | RFC 9110 |
| origin server | 원본 서버 | 대상 리소스에 대해 권한 있는 응답을 만들어 내는 서버(3.6절). origin(출처)과는 따로 옮김 | RFC 9110 |
| origination date | 생성 일시 | 메시지가 생성된 날짜와 시간(`Date`, RFC 5322 `orig-date`) | RFC 9110 |
| orthogonal | 직교 | 서로 독립적임(15.4.1·16.1.2절). TTA·정보통신기술용어해설 같음 | 공통 |
| outstanding request | 미처리 요청 | rfc9110.md와 같게(9.2절) | 공통 |
| overflow | 오버플로 | 관용 표기(번역자 결정). TTA: 넘침. 정보통신기술용어해설: 오버플로, 오버플로우 | 공통 |
| parameter | 매개 변수 | 이름/값 쌍(5.6.6절). TTA: 매개 변수 | 공통 |
| partial PUT | 부분 PUT | 리소스 상태 일부를 교체하는 PUT(14.5절). 메서드 이름은 원어 | RFC 9110 |
| partial representation | 부분 표현 | 범위 요청으로 받은 표현의 일부(13.1.1절) | RFC 9110 |
| payload | 페이로드 | RFC 9110에서는 content(콘텐츠)로 대체(부록 B.3절). HTTP/2·HTTP/3 프레임의 페이로드는 그대로 페이로드 | 공통 |
| payload body | 페이로드 본문 | RFC 7231의 용어. RFC 9110에서는 content(콘텐츠)로 대체(부록 B.3절) | RFC 9110 |
| peer | 피어 | | 공통 |
| percent-encoding | 퍼센트 인코딩 | 예: 퍼센트 인코딩된 옥텟. TTA: 없음 | 공통 |
| persistent connection | 지속 연결 | | RFC 9110 |
| personally identifiable information | 개인 식별 정보 | 17.8절 | 공통 |
| phishing | 피싱 | TTA·정보통신기술용어해설 같음 | 공통 |
| pipe-and-filter architecture | 파이프 앤드 필터 아키텍처 | | 공통 |
| pipelining | 파이프라이닝 | 정보통신기술용어해설: 파이프라인, 파이프라이닝. TTA 해설 본문도 파이프라이닝 | 공통 |
| point of contact | 연락 창구 | 등록 규칙(16.7절) | 공통 |
| pre-fetching | 미리 가져오기 | 캐시 성능 최적화. TTA·정보통신기술용어해설: 없음 | 공통 |
| precision loss | 정밀도 손실 | | 공통 |
| precondition | 전제 조건 | 조건부 요청의 조건(13.1절). TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| prefix | 접두사 | URI 접두사(15.5.15절). "a prefix of the representation"은 표현의 앞부분(15.3.7.3절). TTA: 앞(앞 표기법), 프리픽스(TTA 표준). 정보통신기술용어해설: 프리픽스, 접두사 | 공통 |
| private agreement | 사적 합의 | 클라이언트와 서버 사이의 비공개 합의(14.4·14.5절) | RFC 9110 |
| private browsing mode | 사생활 보호 브라우징 모드 | 17.14절 | 공통 |
| private key | 개인 키 | TTA: 개인 키 | 공통 |
| privilege escalation | 권한 상승 | TTA·정보통신기술용어해설: 없음 | 공통 |
| proactive negotiation | 사전 협상 | 일명 서버 주도 협상. 요청에 담긴 선호로 서버가 표현을 선택(12.1절) | RFC 9110 |
| product identifier | 제품 식별자 | `User-Agent`, `Server`의 구성 요소(10.1.5절) | RFC 9110 |
| progress bar | 진행 표시줄 | 번역자 결정(제안 표기 확정. 두 사전 모두 해당 항목 없음. 6.1절) | RFC 9112 |
| protection space | 보호 공간 | 출처와 영역 값으로 정의(11.5절). TTA: 없음 | RFC 9110 |
| protocol element | 프로토콜 요소 | RFC 6365 정의 | RFC 9110 |
| proxy | 프록시 | TTA: 프락시 | RFC 9110 |
| pseudo-code | 의사 코드 | 정보통신기술용어해설: 의사 코드, 슈도 코드. TTA: 유사 부호(TTA 표준 TTAS.KO-11.0019는 의사 코드) | 공통 |
| pseudo-parameter | 의사 매개 변수 | `TE`의 "q"(7.3절) | RFC 9112 |
| pseudonym | 가명 | `Via`의 `received-by`에 실제 호스트 대신 쓰는 이름. ABNF 규칙 이름 `pseudonym`은 원어. TTA: 가명 정보 | RFC 9110 |
| quality value | 품질 값 | 가중치 매개 변수 "q"의 값, 0~1(12.4.2절). 줄임말 qvalue와 ABNF 규칙 이름 `qvalue`는 원어 | RFC 9110 |
| quoted string | 따옴표 문자열 | 큰따옴표로 감싼 문자열(5.6.4절). ABNF 규칙 이름 `quoted-string`은 원어. 정보통신기술용어해설: string → 문자열 | RFC 9110 |
| range request | 범위 요청 | | RFC 9110 |
| range specifier | 범위 지정자 | 범위 단위와 짝을 이루는 범위 표현(14.1.1절). ABNF 규칙 이름 `range-spec`, `ranges-specifier`는 원어 | RFC 9110 |
| range unit | 범위 단위 | 범위를 세는 단위, 예: bytes(14.1절). ABNF 규칙 이름 `range-unit`은 원어 | RFC 9110 |
| re-identification | 재식별 | 동사는 재식별하다. TTA: 재식별화. 정보통신기술용어해설: 해당 항목 없음 | 공통 |
| reactive negotiation | 사후 협상 | 일명 에이전트 주도 협상. 첫 응답을 받은 뒤 사용자 에이전트가 선택(12.2절) | RFC 9110 |
| realm | 영역 | 매개 변수 이름 `realm`은 원어. 첫 등장에 "영역(realm)". TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| reason phrase | 이유 구문 | 상태 코드 뒤의 설명 문구(6.2절). TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| recipient | 수신자 | | 공통 |
| redirect | 리다이렉트 | 3xx 응답으로 다른 URI를 가리키는 것. TTA: HTTP 리다이렉트 항목 없음 | RFC 9110 |
| redirection | 리다이렉션 | 리다이렉트하는 일. `3xx (Redirection)` 클래스 이름은 원어 | RFC 9110 |
| reference identity | 참조 식별자 | 인증서와 비교할 기대 신원(RFC 6125). 유형 이름 IP-ID, DNS-ID, CN-ID는 원어 유지 | RFC 9110 |
| referrer | 리퍼러 | 대상 URI를 얻은 리소스. 헤더 필드 이름은 철자가 틀린 `Referer`(원어). TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| registered name | 등록된 이름 | URI의 호스트가 IP 주소가 아닌 이름일 때 | 공통 |
| registration form | 등록 양식 | IANA 등록 양식(14.6절). 항목 이름은 원어 병기 | 공통 |
| registration procedure | 등록 절차 | IANA 레지스트리의 등록 방법(16·18장) | 공통 |
| registry | 레지스트리 | TTA·정보통신기술용어해설 같음. 레지스트리 이름은 번역하고 처음 나올 때 원어 병기(아래 "IANA 레지스트리 이름" 표) | 공통 |
| remote method invocation | 원격 메서드 호출 | TTA: 자바 원격 메소드 호출(Java RMI). method는 "메서드"로 통일 | 공통 |
| replay attack | 재전송 공격 | TTA: 재전송 공격. 정보통신기술용어해설: 재생 공격, 재전송 공격 | 공통 |
| representation | 표현 | | RFC 9110 |
| representation metadata | 표현 메타데이터 | 콘텐츠를 어떻게 해석할지 설명하는 메타데이터(8장). TTA: metadata → 메타데이터 | RFC 9110 |
| request | 요청 | | 공통 |
| request content negotiation | 요청 콘텐츠 협상 | 응답에 선호를 담아 이후 요청의 콘텐츠 선택에 영향을 줌(12.3절) | RFC 9110 |
| request loop | 요청 루프 | | RFC 9110 |
| request modifier | 요청 수정자 | 요청 의미를 바꾸는 헤더 필드 등 | RFC 9110 |
| request smuggling | 요청 스머글링 | 중개자와 서버가 메시지 경계를 다르게 해석하는 점을 이용한 공격. TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| request target | 요청 대상 | | RFC 9110 |
| request-line | 요청 줄 | ABNF 규칙 이름 `request-line`은 원어 | RFC 9112 |
| request-target | 요청 대상 | ABNF 규칙 이름 `request-target`은 원어. 형식 이름 origin-form, absolute-form, authority-form, asterisk-form은 원어(3.2절 제목) | RFC 9112 |
| resource | 리소스 | | RFC 9110 |
| response | 응답 | | 공통 |
| response correlation | 응답 대응 | 요청 메시지와 응답 메시지를 짝짓는 것(7.5절) | RFC 9110 |
| response splitting | 응답 분할 | TTA·정보통신기술용어해설: 없음 | 공통 |
| responsible party | 책임 당사자 | 등록 규칙(16.7절) | 공통 |
| retry | 재시도 | | 공통 |
| reverse proxy | 리버스 프록시 | 게이트웨이의 다른 이름. TTA: 역 프락시 캐시(reverse proxy cache). proxy는 관용인 프록시로 통일 | RFC 9110 |
| revision control | 개정 관리 | | 공통 |
| robustness | 강건성 | TTA: 강건성(데이터 강건성). 정보통신기술용어해설: 견실성, 강인성, 강건성. 형용사 robust는 "강건한", 부사는 "강건하게" | 공통 |
| round trip | 왕복 | 예: 추가 왕복. TTA·정보통신기술용어해설: 왕복 시간(RTT) | 공통 |
| safe (method) | 안전한 (메서드) | 정의된 의미가 본질적으로 읽기 전용(9.2.1절) | RFC 9110 |
| safe method | 안전한 메서드 | | RFC 9110 |
| satisfiable / unsatisfiable | 충족 가능 / 충족 불가능 | 범위 지정자가 선택된 표현에 대해 충족되는지(14.1.1절). 상태 코드 `416 (Range Not Satisfiable)`은 원어 | RFC 9110 |
| secondary resource | 2차 리소스 | 프래그먼트 식별자로 간접 식별되는 리소스 | 공통 |
| secured connection | 보안 처리된 연결 | 예: TLS로 보안 처리된 연결(RFC 9112 3.3·9.7절). secure connection(보안 연결)과 구분 | 공통 |
| selected representation | 선택된 표현 | 콘텐츠 협상으로 고른 표현 | RFC 9110 |
| selecting header field | 선택 헤더 필드 | `Vary`에 나열되는 요청 필드(12.5.5절) | RFC 9110 |
| self-descriptive | 자기 서술적 | 예: 자기 서술적 메시지 | RFC 9110 |
| semantics | 의미론 | | RFC 9110 |
| semaphore | 세마포어 | TTA 용어사전·정보통신기술용어해설 같음. TTA 표준에는 신호기, 세머포 | 공통 |
| sender | 송신자 | | 공통 |
| server | 서버 | | 공통 |
| server-driven negotiation | 서버 주도 협상 | proactive negotiation의 다른 이름(12.1절) | RFC 9110 |
| server-wide | 서버 전체 | "server-wide OPTIONS request"는 서버 전체 `OPTIONS` 요청(3.2절) | RFC 9112 |
| shared cache | 공유 캐시 | | RFC 9110 |
| short-circuit | 건너뛰다 | 동사. 뒤 단계를 생략한다는 뜻(13.1.5절). 정보통신기술용어해설: 단락 평가, 숏컷(지름길), 단축 평가. TTA: 해당 항목 없음(전기 단락만) | 공통 |
| side effect | 부작용 | 정보통신기술용어해설: 부수 효과, 부가 효과, 부작용. TTA: 없음 | 공통 |
| single part / multiple parts | 단일 파트 / 다중 파트 | `206` 응답이 전송하는 범위 수(15.3.7.1·15.3.7.2절) | RFC 9110 |
| singleton field | 단일 값 필드 | 구성원 하나만 예상하는 필드(5.5절). TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| source | 원천 / 곳 | origin(출처)과 겹치지 않게 옮김. 예: 원래 표현의 원천(8.7절), 신뢰할 수 없는 곳(4.2.4절) | 공통 |
| spider | 스파이더 | 웹을 돌아다니는 로봇. TTA: 스파이더링(spidering), 웹 크롤러(web crawler) | RFC 9110 |
| squatting | 선점 | 쓰지 않으면서 이름을 차지함(16.3.2.1절). TTA: 사이버스쿼팅(도메인 점거) 항목만. 정보통신기술용어해설: 해당 항목 없음 | 공통 |
| start-line | 시작 줄 | 요청 줄 또는 상태 줄(2.1절). ABNF 규칙 이름 `start-line`은 원어 | RFC 9112 |
| state-changing | 상태를 바꾸는 | "state-changing method"는 상태를 바꾸는 메서드 | RFC 9110 |
| stateless | 무상태 | 요청 사이의 상태 정보를 유지하지 않음. 연결 상태와는 무관(HTTP/2는 연결 위에서 스트림 상태를 관리함). 상태 비저장이라고도 함. 문서에서 처음 나올 때 "무상태(stateless, 요청 사이의 상태 정보를 유지하지 않는)"로 풀이. TTA: 무상태 | RFC 9110 |
| status code | 상태 코드 | | RFC 9110 |
| status monitor | 상태 모니터 | 처리 상태를 알려 주는 리소스(15.3.3절) | RFC 9110 |
| status-line | 상태 줄 | ABNF 규칙 이름 `status-line`은 원어 | RFC 9112 |
| strong comparison / weak comparison | 강한 비교 / 약한 비교 | 엔터티 태그 비교 함수(8.8.3.2절) | RFC 9110 |
| strong validator / weak validator | 강한 검증자 / 약한 검증자 | 8.8.1절 | RFC 9110 |
| subproduct | 하위 제품 | | RFC 9110 |
| subrange | 하위 범위 | 표현 데이터를 나눈 일부 범위(14.1절) | RFC 9110 |
| subtag | 하위 태그 | 예: 주 언어 하위 태그 | 공통 |
| suffix | 접미사 | 관용 표기(번역자 결정). `suffix-range`는 표현 데이터 끝부분의 범위(14.1.1절). TTA: 접미부(TTA 표준), 후치(후치 표기법). 정보통신기술용어해설: 접미사(DNS 접미사), 후치(순환 후치) | 공통 |
| superset | 초집합 | 정보통신기술용어해설 표기. TTA: 해당 항목 없음 | 공통 |
| synchronize | 동기화하다 | TTA: 동기(용어사전), 동기화(TTA 표준). 정보통신기술용어해설: 동기, 동기화 | 공통 |
| target resource | 대상 리소스 | 요청이 향하는 리소스(7.1절). TTA: 없음 | RFC 9110 |
| target URI | 대상 URI | | RFC 9110 |
| tear-down | 연결 해제 | 9.6절 제목 | RFC 9112 |
| timeout | 타임아웃 | 예: 비활성 타임아웃. 정보통신기술용어해설: 타임아웃 | 공통 |
| timestamp | 타임스탬프 | TTA: 타임스탬프 | 공통 |
| token | 토큰 | 공백·구분 문자를 포함하지 않는 짧은 텍스트 식별자(5.6.2절). ABNF 규칙 이름 `token`은 원어. TTA: 토큰 | 공통 |
| trailer field | 트레일러 필드 | | RFC 9110 |
| transcoder | 트랜스코더 | TTA·정보통신기술용어해설: 없음 | 공통 |
| transfer coding | 전송 코딩 | content coding(콘텐츠 코딩)과 맞춤. TTA·정보통신기술용어해설: 없음 | RFC 9110 |
| transforming proxy | 변형 프록시 | 메시지를 의미상 중요한 방식으로 수정하는 프록시(7.7절) | RFC 9110 |
| Transparent Content Negotiation | 투명한 콘텐츠 협상 | [RFC2295]의 협상 방식 이름(12장) | RFC 9110 |
| transparent proxy | 투명 프록시 | interception proxy와 같은 뜻 | RFC 9110 |
| trust anchor | 신뢰 앵커 | TTA: 신뢰 앵커 | 공통 |
| tunnel | 터널 | | RFC 9110 |
| tunnel mode | 터널 모드 | `CONNECT` 성공 후 연결 상태 | RFC 9110 |
| underlying (connection/transport) | 기반 (연결/전송) | rfc9110.md와 같게. "하부"로 쓰지 않음 | 공통 |
| uniform interface | 일관된 인터페이스 | | RFC 9110 |
| union | 합집합 | TTA·정보통신기술용어해설 같음 | 공통 |
| upgrade | 업그레이드 | 헤더 필드 이름 `Upgrade`는 원어 | RFC 9110 |
| URI reference | URI 참조 | | 공통 |
| URI scheme | URI 스킴 | 예: http, https. 스킴 이름은 원어 유지 | 공통 |
| user agent | 사용자 에이전트 | | RFC 9110 |
| userinfo | userinfo | URI 구성 요소 이름이므로 원어 유지 | 공통 |
| validator | 검증자 (HTTP 문맥) | HTTP에서는 조건부 요청에 쓰는 표현 메타데이터(`ETag`, `Last-Modified` 등). 예: 불투명한(opaque) 검증자. 그 밖의 문맥에서는 사람·주체면 검증자, 유틸리티·프로그램이면 유효성 검사기. TTA: 검증자(주체), 검사기(소프트웨어) | RFC 9110 |
| version control repository | 버전 관리 저장소 | | 공통 |
| versioning | 버전 관리 | TTA: WebDAV(웹다브) 항목만 | 공통 |
| vulnerability | 취약점 | 정보통신기술용어해설 표기. TTA: 취약성. 구체적인 약점은 "취약점", 공격받기 쉬운 성질(vulnerability to …)은 "취약성"으로 문맥에 따라 나눈다. 본문(5.4·17.5절)에서는 "더 취약해진다"처럼 풀어 씀. "vulnerable"은 취약한 | 공통 |
| web traversal | 웹 순회 | 웹 리소스를 차례로 방문하는 것(8.8.1·13.1.3절) | RFC 9110 |
| weight | 가중치 | 상대적 선호도(12.4.2절) | RFC 9110 |
| well-formed | 형식이 올바른 | malformed(형식이 잘못된)의 반대(15.5.21절) | 공통 |
| whitespace | 공백 | OWS(선택적 공백), RWS(필수 공백), BWS("나쁜" 공백). 규칙 이름은 원어. 정보통신기술용어해설: 공백 문자 | 공통 |
| wildcard | 와일드카드 | 관용 표기(번역자 결정). 지정되지 않은 값을 고르는 "*"(12.4.3절). TTA: 와일드 카드 문자. 정보통신기술용어해설: 와일드카드 마스크 | 공통 |
| wire format, on the wire | 와이어 포맷, 와이어상 | 데이터를 네트워크나 시스템 간에 전송하기 위해 바이트 단위로 직렬화하거나 인코딩하는 표준 규칙과 구조. 억지로 한글로 옮기지 않고 발음대로 표기 | RFC 9110 |
| workaround | 우회책 | | RFC 9110 |

## IANA 레지스트리 이름 

문서에서 처음 나올 때 원어를 병기한다. 따옴표는 원문이 쓴 곳에만 둔다. 이름에 Registry가 없으면 "레지스트리"를 붙이지 않는다(원문 문장에 registry가 따로 있으면 문장 쪽에 둔다).

| 원어 | 번역어 | 비고 | 범위 |
|---|---|---|---|
| HTTP Content Coding Registry | HTTP 콘텐츠 코딩 레지스트리 | | RFC 9110 |
| HTTP Method Registry | HTTP 메서드 레지스트리 | RFC 9113 11장의 표기. RFC 9110의 "Hypertext Transfer Protocol (HTTP) Method Registry"와 같은 레지스트리 | RFC 9113 |
| HTTP Range Unit Registry | HTTP 범위 단위 레지스트리 | | RFC 9110 |
| HTTP Transfer Coding Registry | HTTP 전송 코딩 레지스트리 | | 공통 |
| HTTP/2 Error Code | HTTP/2 오류 코드 | 원문은 "the … registry"라서 "HTTP/2 오류 코드" 레지스트리 | RFC 9113 |
| HTTP/2 Frame Type | HTTP/2 프레임 유형 | 원문은 "the … registry"라서 "HTTP/2 프레임 유형" 레지스트리 | RFC 9113 |
| HTTP/2 Settings | HTTP/2 설정 | 원문은 "the … registry"라서 "HTTP/2 설정" 레지스트리 | RFC 9113 |
| Hypertext Transfer Protocol (HTTP) Authentication Scheme Registry | HTTP 인증 스킴 레지스트리 | | RFC 9110 |
| Hypertext Transfer Protocol (HTTP) Field Name Registry | HTTP 필드 이름 레지스트리 | | 공통 |
| Hypertext Transfer Protocol (HTTP) Method Registry | HTTP 메서드 레지스트리 | | RFC 9110 |
| Hypertext Transfer Protocol (HTTP) Status Code Registry | HTTP 상태 코드 레지스트리 | | RFC 9110 |
| Hypertext Transfer Protocol (HTTP) Upgrade Token Registry | HTTP 업그레이드 토큰 레지스트리 | | RFC 9110 |
| Media Types | 미디어 유형 | 원문은 "the "Media Types" registry"라서 "미디어 유형" 레지스트리 | 공통 |
| Permanent Message Header Field Names | 영구 메시지 헤더 필드 이름 | 상태 값 'permanent'는 원어 | RFC 9110 |
| Provisional Message Header Field Names | 임시 메시지 헤더 필드 이름 | 상태 값 'provisional'은 원어 | RFC 9110 |
| Service Name and Transport Protocol Port Number Registry | 서비스 이름 및 전송 프로토콜 포트 번호 레지스트리 | | RFC 9110 |
| TLS Application-Layer Protocol Negotiation (ALPN) Protocol IDs | TLS ALPN 프로토콜 ID | | RFC 9112 |
| Uniform Resource Identifier (URI) Schemes | URI 스킴 | | RFC 9110 |

## HTTP/2

| 원어 | 번역어 | 비고 | 출처 |
|---|---|---|---|
| acknowledge (ACK) | 확인 응답 | 플래그 이름 `ACK`는 원어 유지 | RFC 9113 |
| advertise | (상대에게) 알리다 | "광고하다"로 옮기지 않음. 예: 알린 흐름 제어 윈도우 | RFC 9113 |
| alternative service | 대체 서비스 | [ALT-SVC] (9.1절). 두 사전 모두 없음(2026-10-20 조회). 번역자 결정(2026-10-20, 표기 유지) | RFC 9113 |
| bandwidth * delay product | 대역폭 * 지연 | 번역자 결정(2026-10-20). 정보통신기술용어해설: 대역폭 지연 곱, TTA 없음(5.2.2절) | RFC 9113 |
| boolean | 불리언 | 정보통신기술용어해설: 불리언 값·부울 값, TTA: 불(6.5절) | RFC 9113 |
| cipher suite | 암호 스위트 | 정보통신기술용어해설 암호 용어 항목(no=4240)에 "Cipher Suite, 암호 스위트". 스위트 이름(TLS_…)은 원어 | RFC 9113 |
| ciphertext | 암호문 | 두 사전 같음(10.6절) | RFC 9113 |
| cleartext | 평문 | TLS를 쓰지 않는 연결 | RFC 9113 |
| closed | `closed` | 스트림 상태 이름. 아래 "스트림 상태 이름" 참고 | RFC 9113 |
| codepoint | 코드 포인트 | 정보통신기술용어해설 표기(Code Point), TTA 없음(부록 B) | RFC 9113 |
| compression context | 압축 컨텍스트 | 두 사전 모두 없음. context는 정보통신기술용어해설 "컨텍스트"(4.3절) | RFC 9113 |
| congestion window | 혼잡 윈도우 | 정보통신기술용어해설 표기. flow-control window(흐름 제어 윈도우)와 같은 "윈도우" (번역자 결정, 2026-10-20) | RFC 9113 |
| connection coalescing | 연결 병합 | coalesce(병합하다, RFC 9110)에 맞춤. 두 사전 모두 없음(부록 B) | RFC 9113 |
| connection error | 연결 오류 | | RFC 9113 |
| connection preface | 연결 프리페이스 | 연결 시작 시 보내는 고정 시퀀스 | RFC 9113 |
| connection-oriented | 연결 지향 | 정보통신기술용어해설: 연결지향성·연결지향적, TTA: 연결형(용어사전)·연결 지향성(TTA 표준)(2장) | RFC 9113 |
| connection-specific header field | 연결 전용 헤더 필드 | (8.2.2절) | RFC 9113 |
| cookie-pair | 쿠키 쌍 | "crumbs"는 부스러기(8.2.3절) | RFC 9113 |
| credit | 크레딧 | 흐름 제어 크레딧(5.1·5.2.1절). 두 사전 모두 이 뜻의 항목 없음(2026-10-20 조회). 번역자 결정(2026-10-20, 표기 유지) | RFC 9113 |
| cross-protocol attack | 교차 프로토콜 공격 | 10.2절. 두 사전 모두 없음(2026-10-20 조회). 번역자 결정(2026-10-20, 표기 유지) | RFC 9113 |
| deadlock | 교착 상태 | 5.2.2절. 두 사전 같음 | RFC 9113 |
| deployment | 배포 | 두 사전 모두 이 뜻의 항목 없음(5.2.2절) | RFC 9113 |
| dynamic table | 동적 테이블 | HPACK 컨텍스트의 주된 상태(4.3.1절, [COMPRESSION] 4장) | RFC 9113 |
| Dynamic Table Size Update | 동적 테이블 크기 갱신 | [COMPRESSION] 6.3절의 명령 이름. 처음 나올 때 원어 병기(4.3.1절) | RFC 9113 |
| early data | 조기 데이터 | TLS 1.3 early data(9.2.3절). 두 사전 모두 없음(2026-10-20 조회). 번역자 결정(2026-10-20, 표기 유지) | RFC 9113 |
| elliptic curve | 타원 곡선 | TTA 표준 표기, 정보통신기술용어해설 없음(9.2.1절) | RFC 9113 |
| ephemeral | 임시 | 임시 키 교환(9.2.1절). 두 사전 같음(임시 키, 임시 포트번호) | RFC 9113 |
| error code | 오류 코드 | 코드 이름은 원어 유지 | RFC 9113 |
| extension | 확장 | | RFC 9113 |
| field block | 필드 블록 | | RFC 9113 |
| field block fragment | 필드 블록 조각 | | RFC 9113 |
| field compression | 필드 압축 | 두 사전 모두 없음. compression은 압축(요약, 4.3.1절) | RFC 9113 |
| field section | 필드 섹션 | | RFC 9113 |
| field section compression | 필드 섹션 압축 | 반대는 필드 섹션 압축 해제(4.3절). [COMPRESSION]은 헤더 압축이라고 부름 | RFC 9113 |
| finite field | 유한체 | 두 사전 같음(9.2.1절) | RFC 9113 |
| flags | 플래그 | | RFC 9113 |
| flow control | 흐름 제어 | | RFC 9113 |
| flow-control window | 흐름 제어 윈도우 | | RFC 9113 |
| frame | 프레임 | | RFC 9113 |
| frame header | 프레임 헤더 | 고정 9옥텟(4.1절). 필드 이름 Length, Type, Flags, Reserved, Stream Identifier는 원어 | RFC 9113 |
| frame payload | 프레임 페이로드 | 4.1절 | RFC 9113 |
| frame type | 프레임 유형 | 유형 이름은 원어 유지 | RFC 9113 |
| graceful shutdown | 우아한 종료 | graceful close(RFC 9112)와 같은 번역어. 두 사전 모두 없음(5.4절) | RFC 9113 |
| half-closed (local/remote) | `half-closed (로컬)` / `half-closed (원격)` | 스트림 상태 이름. 처음 나올 때 "한쪽 방향만 닫힌 상태"로 풀이 | RFC 9113 |
| header compression | 헤더 압축 | | RFC 9113 |
| hop | 홉 | 5.2.1절. hop by hop은 홉 단위. 두 사전 같음 | RFC 9113 |
| HPACK decoder context | HPACK 디코더 컨텍스트 | (4.3.1절) | RFC 9113 |
| HPACK encoder context | HPACK 인코더 컨텍스트 | (4.3.1절) | RFC 9113 |
| idle | `idle` | 스트림 상태 이름 | RFC 9113 |
| interleaving | 인터리빙 | 정보통신기술용어해설 표기. TTA: 끼우기(interleave)(1장) | RFC 9113 |
| key exchange | 키 교환 | 두 사전 같음. 임시 키 교환(ephemeral key exchange)(9.2.1절) | RFC 9113 |
| keying material | 키 재료 | 9.1절. TTA 표준 표기(키 자료도 있음), 정보통신기술용어해설 없음 | RFC 9113 |
| load balancer | 로드 밸런서 | load balancing(부하 분산)과 구분. TTA: 서버 부하 분산 장치, 정보통신기술용어해설 없음(8.7절) | RFC 9113 |
| malformed | 형식이 잘못된 | 예: 형식이 잘못된 요청 | RFC 9113 |
| middlebox | 미들박스 | 8.7절. 번역자 결정(2026-10-20). TTA: 중간 장비, 정보통신기술용어해설 없음 | RFC 9113 |
| multiplexing | 다중화 | | RFC 9113 |
| network address translator | 네트워크 주소 변환기 | 두 사전 모두 없음(8.7절) | RFC 9113 |
| network byte order | 네트워크 바이트 순서 | 정보통신기술용어해설 표기, TTA 없음(2.2절) | RFC 9113 |
| opaque data | 불투명한 데이터 | `PING`(6.7절), `GOAWAY`(6.8절). 필드 이름 Opaque Data는 원어 | RFC 9113 |
| open | `open` | 스트림 상태 이름 | RFC 9113 |
| opportunity cost | 기회비용 | 8.4절 | RFC 9113 |
| out-of-band | 대역 외 | 두 사전 같음(3장) | RFC 9113 |
| padding | 패딩 | | RFC 9113 |
| plaintext | 평문 | cleartext와 같은 번역어. 두 사전 같음(10.2절) | RFC 9113 |
| post-handshake | 핸드셰이크 후 | 두 사전 모두 없음(9.2.3절) | RFC 9113 |
| prior knowledge | 사전 지식 | HTTP/2 지원을 미리 아는 경우 | RFC 9113 |
| prioritization | 우선순위 지정 | priority(우선순위)에서 만든 말(1장) | RFC 9113 |
| priority | 우선순위 | RFC 9113에서 RFC 7540의 우선순위 체계는 폐기됨 | RFC 9113 |
| promised stream | 약속된 스트림 | 서버 푸시용 | RFC 9113 |
| pseudo-header field | 의사 헤더 필드 | 예: `:method`, `:path` | RFC 9113 |
| race condition | 경쟁 상태 | 6.8절. 번역자 결정(2026-10-20). TTA 표기, 정보통신기술용어해설: 경쟁 조건 | RFC 9113 |
| receiver | 수신자 | recipient(수신자)와 같은 번역어(번역자 결정, 2026-10-20). 2.2절 정의 용어("프레임을 받는 엔드포인트"). 원문도 SETTINGS 프레임을 받는 쪽을 receiver와 recipient로 섞어 씀 | RFC 9113 |
| renegotiation | 재협상 | TLS 재협상(9.2.1절). 두 사전 모두 없음(2026-10-20 조회). 번역자 결정(2026-10-20, 표기 유지) | RFC 9113 |
| reserved (local/remote) | `reserved (로컬)` / `reserved (원격)` | 스트림 상태 이름 | RFC 9113 |
| round-trip time | 왕복 시간 | 5.4.2절. 두 사전 같음 | RFC 9113 |
| server push | 서버 푸시 | | RFC 9113 |
| setting | 설정 | `SETTINGS` 프레임의 구성 매개 변수 하나(6.5절). 설정 이름은 원어(`SETTINGS_…`) | RFC 9113 |
| stateful | 상태를 가지는 | 예: 필드 압축은 상태를 가진다(4.3.1절) | RFC 9113 |
| stream | 스트림 | | RFC 9113 |
| stream error | 스트림 오류 | | RFC 9113 |
| stream identifier | 스트림 식별자 | | RFC 9113 |
| stream state | 스트림 상태 | | RFC 9113 |
| tenant | 테넌트 | 10.4절. TTA 표기, 정보통신기술용어해설 없음 | RFC 9113 |
| TLS termination | TLS 터미네이션 | 번역자 결정(2026-10-20). 클라이언트와 서버 사이의 암호화된 통신(TLS)을 서버 앞단(로드 밸런서, 리버스 프록시 등)에서 대신 복호화해 끝내고, 내부 네트워크로는 평문(HTTP)으로 전달하는 것. 연결 종료와 구분. 두 사전 모두 없음(9.1.1절) | RFC 9113 |

### 스트림 상태 이름

RFC 9113 5.1절의 상태 전이 다이어그램은 번역하지 않으므로, 본문의 상태 이름도 다이어그램과 같은 원어로 둡니다.

- 상태 이름 `idle`, `open`, `reserved`, `half-closed`, `closed`는 원어 그대로 코드 서식으로 씁니다.
- 괄호 안의 local, remote만 **로컬, 원격**으로 옮깁니다. 예: `half-closed (로컬)`, `reserved (원격)`
- 문서에서 처음 나올 때 뜻을 풀어 줍니다. 예: `half-closed`(한쪽 방향만 닫힌 상태)
- 상태가 아닌 일반 서술(예: "the connection is closed")은 평소처럼 "닫힌", "열린"으로 옮깁니다.

> 예: 엔드포인트가 `END_STREAM` 플래그를 보내면 스트림 상태가 `half-closed (로컬)`이 되고, 받으면 `half-closed (원격)`이 된다.

## 원어 그대로 두는 것

번역하지 않고 코드 서식(`` ` ``)으로 표기합니다.

- 프레임 유형: `DATA`, `HEADERS`, `PRIORITY`, `RST_STREAM`, `SETTINGS`, `PUSH_PROMISE`, `PING`, `GOAWAY`, `WINDOW_UPDATE`, `CONTINUATION`
- 플래그: `END_STREAM`, `END_HEADERS`, `PADDED`, `PRIORITY`, `ACK`
- 오류 코드: `NO_ERROR`, `PROTOCOL_ERROR`, `FLOW_CONTROL_ERROR`, `STREAM_CLOSED` 등
- 설정 이름: `SETTINGS_MAX_CONCURRENT_STREAMS`, `SETTINGS_INITIAL_WINDOW_SIZE` 등
- 의사 헤더: `:method`, `:scheme`, `:authority`, `:path`, `:status`
- 스트림 상태: `idle`, `open`, `reserved (로컬/원격)`, `half-closed (로컬/원격)`, `closed` (괄호 안만 한국어)
- HTTP 메서드, 헤더 필드 이름, 상태 코드 이름, ABNF 규칙 이름

코드 서식 없이 원어로 두는 이름: TLS, ALPN, SNI(Server Name Indication), HPACK, QUIC. 처음 나올 때 원문의 풀어 쓴 이름이 있으면 그대로 둡니다.

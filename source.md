# n8n으로 시작하는 업무 자동화
## 초급 과정 Day 1

---

## 오늘 배울 내용

- 자동화가 필요한 이유 (15분)
- n8n 시작하기 (15분)
- **실습 8개** (4시간)
- 자유 실습 시간 (30분)

**목표: 오늘 최소 5개 이상의 자동화를 직접 만듭니다**

---

## 이런 일, 매일 하고 계신가요?

- 📧 이메일 확인하고 중요한 것만 따로 정리
- 📊 여러 곳 데이터를 엑셀에 복사-붙여넣기
- 💬 특정 메시지가 오면 담당자에게 전달
- 📋 매주 같은 양식의 보고서 작성
- 🔔 중요한 알림을 여러 곳에서 확인

**이 모든 것, 오늘 자동화합니다**

---

## 자동화 = 규칙이 있는 반복 작업을 컴퓨터에게 맡기는 것

**예시: 이메일 → 슬랙 알림**

수동으로 할 때:
1. 이메일 열기
2. 제목에 "긴급" 있는지 확인
3. 슬랙 열기
4. 메시지 작성해서 전송

자동화 후:
→ 컴퓨터가 1초 만에 처리

---

## n8n이란?

**블록 조립하듯 자동화 만드는 도구**

- 800개 이상의 앱/서비스 연동
- 코딩 불필요
- 무료 오픈소스
- 클라우드/셀프호스팅 모두 가능

**오늘은 클라우드 서버로 진행합니다**

---

## n8n의 3가지 핵심 개념

**1. 워크플로우 (Workflow)**
- 자동화의 전체 시나리오

**2. 노드 (Node)**
- 각각의 작업 단위 (레고 블록)

**3. 트리거 (Trigger)**
- 자동화를 시작시키는 신호

---

## 모든 워크플로우의 기본 구조

```
[트리거] → [작업] → [작업] → [결과]
```

**구체적 예시:**
```
[매일 9시] → [날씨 확인] → [메시지 작성] → [이메일 전송]
```
```
[폼 제출] → [데이터 정리] → [저장] → [알림]
```

---

## 실습 준비: n8n 접속

**접속 정보**
- URL: `[실제 서버 주소]`
- ID: `[제공된 계정]`
- PW: `[제공된 비밀번호]`

**모두 로그인 화면 보이시나요?**

---

## n8n 화면 구성

**왼쪽**: 노드 라이브러리 (사용 가능한 모든 블록)
**중앙**: 캔버스 (여기서 작업합니다)
**오른쪽**: 설정 패널 (선택한 노드의 상세 설정)
**상단**: 실행/저장 버튼

**각자 화면을 둘러봐주세요 (2분)**

---

## 실습 1: Hello World 만들기
### 가장 간단한 워크플로우

**목표**: 버튼 누르면 메시지 출력
**노드**: 2개 (Manual Trigger + Set)
**시간**: 10분

---

## 실습 1 - Step 1: 워크플로우 생성

1. 좌측 상단 **"+ New Workflow"** 클릭
2. 워크플로우 이름 클릭
3. 이름 변경: `"실습1_Hello_World"`

**Tip**: 이름을 잘 지어두면 나중에 찾기 쉽습니다

---

## 실습 1 - Step 2: Manual Trigger 추가

캔버스 중앙의 **+** 버튼 클릭
→ 검색창에 `manual` 입력
→ **"Manual Trigger"** 선택

**이 노드는 "실행" 버튼을 누르면 작동합니다**

---

## 실습 1 - Step 3: Set 노드 연결

Manual Trigger 노드 오른쪽의 **+** 버튼 클릭
→ 검색창에 `set` 입력
→ **"Set"** 선택

**두 노드가 선으로 연결되었나요?**

---

## 실습 1 - Step 4: 데이터 입력

Set 노드 클릭 → 우측 패널 확인
→ **"Add Value"** 클릭
→ Name: `message`
→ Value: `안녕하세요, n8n 세계에 오신 것을 환영합니다!`

---

## 실습 1 - Step 5: 실행!

좌측 상단 **"Execute Workflow"** 버튼 클릭
→ Set 노드 클릭하여 결과 확인

**축하합니다! 첫 워크플로우 완성** 🎉

---

## 방금 만든 것의 의미

```
[버튼 클릭] → [데이터 생성] → [결과 출력]
```

단순해 보이지만:
- 트리거의 개념 이해
- 노드 연결 방법 학습
- 데이터 흐름 확인

**모든 복잡한 자동화도 이 기본 원리입니다**

---

## 실습 2: 여러 데이터 한 번에 만들기
### Set 노드 심화

**목표**: 여러 종류의 데이터를 한 번에 생성
**노드**: 2개 (Manual Trigger + Set)
**시간**: 10분

---

## 실습 2 - Step 1: 새 워크플로우

**"+ New Workflow"** 클릭
이름: `"실습2_다중데이터"`

Manual Trigger 추가 (이제 익숙하시죠?)

---

## 실습 2 - Step 2: Set 노드에 여러 값 추가

Set 노드 연결 후:

1. **Add Value** → Name: `name`, Value: `홍길동`
2. **Add Value** → Name: `email`, Value: `hong@example.com`
3. **Add Value** → Name: `age`, Value: `25` (숫자)
4. **Add Value** → Name: `city`, Value: `서울`

---

## 실습 2 - Step 3: 실행 및 확인

**Execute Workflow** 클릭
→ Set 노드에서 결과 확인

**JSON 형식으로 데이터가 정리되어 있습니다**
```json
{
  "name": "�홍길동",
  "email": "hong@example.com",
  "age": 25,
  "city": "서울"
}
```

---

## 실습 3: 계산하기
### Code 노드 체험

**목표**: 간단한 계산을 코드로 해보기
**노드**: 3개 (Manual Trigger + Set + Code)
**시간**: 15분

**겁먹지 마세요! 복사-붙여넣기만 하면 됩니다**

---

## 실습 3 - Step 1: 준비

새 워크플로우: `"실습3_계산기"`

1. Manual Trigger 추가
2. Set 노드 추가
   - Name: `price`, Value: `50000`
   - Name: `quantity`, Value: `3`

---

## 실습 3 - Step 2: Code 노드 추가

Set 노드 오른쪽 **+** 클릭
→ `code` 검색
→ **"Code"** 선택

---

## 실습 3 - Step 3: 코드 입력

우측 패널의 코드 영역에 다음을 입력:

```javascript
// 이전 노드에서 데이터 가져오기
const price = $input.item.json.price;
const quantity = $input.item.json.quantity;

// 계산하기
const total = price * quantity;
const vat = total * 0.1;
const finalPrice = total + vat;

// 결과 반환
return {
  json: {
    original_price: price,
    quantity: quantity,
    subtotal: total,
    vat: vat,
    total_price: finalPrice
  }
};
```

---

## 실습 3 - Step 4: 실행

**Execute Workflow** 클릭
→ Code 노드 결과 확인

**계산 결과:**
- 소계: 150,000원
- 부가세: 15,000원
- 총액: 165,000원

---

## Code 노드 설명

**언제 사용하나요?**
- 복잡한 계산
- 데이터 변형
- 조건부 로직
- 기존 노드로 안 되는 작업

**JavaScript 모르면?**
→ ChatGPT/Claude에게 물어보세요!
→ 대부분의 로직은 기존 노드로 해결 가능

---

## 휴식 (10분)

---

## 실습 4: 조건 분기 - 나이 확인
### IF 노드로 조건 만들기

**목표**: 나이에 따라 다른 메시지 출력
**노드**: 4개 (Trigger + Set + IF + Set×2)
**시간**: 15분

---

## 실습 4 - Step 1: 준비

새 워크플로우: `"실습4_나이확인"`

1. Manual Trigger
2. Set 노드
   - Name: `name`, Value: `김철수`
   - Name: `age`, Value: `17`

---

## 실습 4 - Step 2: IF 노드 추가

Set 노드 오른쪽 **+** 클릭
→ `if` 검색
→ **"IF"** 선택

---

## 실습 4 - Step 3: 조건 설정

IF 노드 클릭 → 우측 패널:

**Conditions**:
- Value 1: `{{ $json.age }}`
- Operation: `Larger Than or Equal`
- Value 2: `19`

**19세 이상이면 True, 미만이면 False**

---

## 실습 4 - Step 4: True 경로

IF 노드의 **true** 출력(초록색)에서 **+** 클릭
→ Set 노드 선택
→ Name: `message`
→ Value: `{{ $json.name }}님, 성인입니다. 환영합니다!`

---

## 실습 4 - Step 5: False 경로

IF 노드의 **false** 출력(빨간색)에서 **+** 클릭
→ Set 노드 선택
→ Name: `message`
→ Value: `{{ $json.name }}님, 미성년자입니다.`

---

## 실습 4 - Step 6: 테스트

**Execute Workflow** 클릭
→ False 경로의 Set 노드만 실행됨 (17세라서)

**실험:**
처음 Set 노드의 age를 `25`로 변경
→ 다시 실행
→ 이번엔 True 경로가 실행됨!

---

## IF 노드의 위력

```
[데이터] → [조건 확인]
              ├─ 조건 충족 → [액션 A]
              └─ 조건 불충족 → [액션 B]
```

**실전 활용:**
- 금액이 크면 알림 보내기
- 주말이면 다르게 처리
- 특정 키워드가 있으면 분류

---

## 실습 5: 여러 조건 처리
### Switch 노드로 다중 분기

**목표**: 점수에 따라 등급 나누기
**노드**: 3개 (Trigger + Switch + Set×4)
**시간**: 15분

---

## 실습 5 - Step 1: 준비

새 워크플로우: `"실습5_성적등급"`

1. Manual Trigger
2. Set 노드
   - Name: `student`, Value: `이영희`
   - Name: `score`, Value: `85`

---

## 실습 5 - Step 2: Switch 노드

Set 노드 오른쪽 **+** 클릭
→ `switch` 검색
→ **"Switch"** 선택

---

## 실습 5 - Step 3: 조건 설정

**Mode**: `Rules`

**Rule 1** (A등급):
- Value 1: `{{ $json.score }}`
- Operation: `Larger Than or Equal`
- Value 2: `90`
- Output: `0`

**Rule 2** (B등급):
- Operation: `Larger Than or Equal`
- Value 2: `80`
- Output: `1`

**Rule 3** (C등급):
- Operation: `Larger Than or Equal`
- Value 2: `70`
- Output: `2`

**Rule 4** (D등급):
- Output: `3` (Fallback)

---

## 실습 5 - Step 4: 각 출력에 노드 연결

Switch 노드의 4개 출력에 각각 Set 노드 연결:

**Output 0**: `등급: A - 우수`
**Output 1**: `등급: B - 양호`
**Output 2**: `등급: C - 보통`
**Output 3**: `등급: D - 노력 필요`

---

## 실습 5 - Step 5: 여러 점수로 테스트

점수를 바꿔가며 실행:
- `95` → A 등급
- `85` → B 등급
- `75` → C 등급
- `60` → D 등급

**각각 다른 경로가 실행됩니다**

---

## Switch vs IF

**IF 노드**
- 2개 경로 (True/False)
- 간단한 조건

**Switch 노드**
- 3개 이상 경로
- 복잡한 분류

**실전**: 고객 유형별 처리, 우선순위 분류 등

---

## 점심 시간 (1시간)

---

## 실습 6: 실제 API 사용하기
### 날씨 정보 가져오기

**목표**: OpenWeatherMap API로 실제 날씨 확인
**노드**: 3개 (Schedule Trigger + HTTP Request + Set)
**시간**: 20분

**드디어 외부 세계와 연결합니다!**

---

## API란?

**Application Programming Interface**
= 다른 서비스의 기능을 빌려쓰는 방법

**예시:**
- 날씨 정보 받아오기
- 환율 확인하기
- 지도에서 주소 검색
- 번역하기

**n8n은 API를 쉽게 사용하게 해줍니다**

---

## 실습 6 - 준비: API 키

**OpenWeatherMap API**
- 무료 날씨 정보 제공
- 전 세계 도시 지원

**오늘 사용할 API 키:**
```
[강의용 공용 키 제공]
```

또는 직접 발급: openweathermap.org/api

---

## 실습 6 - Step 1: 워크플로우 생성

새 워크플로우: `"실습6_날씨확인"`

**Schedule Trigger** 추가
- Mode: `Every Day`
- Hour: `9`
- Minute: `0`

**매일 아침 9시에 자동 실행됩니다**

---

## 실습 6 - Step 2: HTTP Request 노드

Schedule Trigger 오른쪽 **+** 클릭
→ `http request` 검색
→ **"HTTP Request"** 선택

---

## 실습 6 - Step 3: API 설정

**Method**: `GET`
**URL**: 
```
https://api.openweathermap.org/data/2.5/weather
```

**Query Parameters** 섹션에서 **Add Parameter** 클릭:
1. Name: `q`, Value: `Seoul`
2. Name: `appid`, Value: `[제공된 API 키]`
3. Name: `units`, Value: `metric`
4. Name: `lang`, Value: `kr`

---

## 실습 6 - Step 4: 테스트 실행

**Execute Workflow** 클릭
→ HTTP Request 노드 클릭
→ 결과 데이터 확인

**실제 서울의 날씨 데이터가 왔습니다!**

---

## 실습 6 - Step 5: 데이터 정리

HTTP Request 오른쪽 **+** 클릭
→ Set 노드 추가

**드래그 앤 드롭으로 값 선택:**
- Name: `city`, 좌측에서 `name` 드래그
- Name: `temperature`, `main.temp` 드래그
- Name: `description`, `weather[0].description` 드래그
- Name: `humidity`, `main.humidity` 드래그

---

## 실습 6 - Step 6: 최종 확인

**Execute Workflow** 클릭
→ Set 노드 결과 확인

**깔끔하게 정리된 날씨 정보:**
```json
{
  "city": "Seoul",
  "temperature": 15.2,
  "description": "맑음",
  "humidity": 45
}
```

---

## 표현식 {{ }} 이해하기

**`{{ $json.name }}`** = 이전 노드의 데이터

- `$json`: 이전 노드 결과
- `.name`: 그 중 name 필드
- `.main.temp`: 계층 구조로 접근

**직접 입력 vs 드래그 앤 드롭**
→ 드래그가 실수 없어서 좋습니다

---

## 실습 7: 날씨 + 조건 결합
### API + IF 노드 조합

**목표**: 날씨가 비오면 다른 메시지
**노드**: 5개 (이전 실습 + IF + Set×2)
**시간**: 15분

**앞에서 배운 것들을 조합합니다!**

---

## 실습 7 - Step 1: 워크플로우 복사

실습6 워크플로우에서:
1. 우측 상단 **...** 메뉴
2. **"Duplicate"** 클릭
3. 이름: `"실습7_날씨알림"`

---

## 실습 7 - Step 2: IF 노드 추가

Set 노드(데이터 정리) 오른쪽 **+** 클릭
→ IF 노드 추가

**조건 설정:**
- Value 1: `{{ $json.description }}`
- Operation: `Contains`
- Value 2: `비`

---

## 실습 7 - Step 3: True 경로

**true** 출력에 Set 노드:

```
이름: alert
값: ☂️ 오늘은 {{ $json.city }}에 비가 옵니다! 
    온도: {{ $json.temperature }}°C
    우산을 챙기세요!
```

---

## 실습 7 - Step 4: False 경로

**false** 출력에 Set 노드:

```
이름: alert
값: ☀️ 오늘 {{ $json.city }} 날씨는 {{ $json.description }}입니다.
    온도: {{ $json.temperature }}°C
    좋은 하루 되세요!
```

---

## 실습 7 - Step 5: 테스트

**Execute Workflow** 클릭
→ 현재 날씨에 따라 다른 메시지 출력

**실험:**
HTTP Request 설정에서 도시를 변경해보세요
- `Tokyo`
- `London`
- `New York`

---

## 지금까지 배운 것들의 조합

```
[스케줄] → [API 호출] → [데이터 정리] → [조건 확인]
                                          ├─ 비 옴 → [우산 알림]
                                          └─ 안 옴 → [일반 알림]
```

**이제 실전 자동화를 만들 준비가 되었습니다!**

---

## 휴식 (10분)

---

## 실습 8: 웹훅으로 외부 연동
### Webhook Trigger 사용하기

**목표**: 외부에서 데이터 받아 처리하기
**노드**: 3개 (Webhook + Set + IF)
**시간**: 20분

**웹훅 = 다른 서비스가 n8n을 부르는 방법**

---

## 웹훅(Webhook)이란?

**일반 트리거**: n8n이 주기적으로 확인
**웹훅**: 외부에서 n8n에게 "이벤트 발생했어!" 알림

**사용 사례:**
- 구글 폼 제출 → n8n 처리
- 결제 완료 → 자동 처리
- 외부 시스템 → n8n 연동

---

## 실습 8 - Step 1: 워크플로우 생성

새 워크플로우: `"실습8_웹훅테스트"`

**Webhook** 트리거 추가
- Path: `test-webhook`
- Method: `POST`

**Test URL이 생성됩니다 - 복사해두세요!**

---

## 실습 8 - Step 2: 데이터 정리

Webhook 노드 오른쪽 **+** 클릭
→ Set 노드 추가

**받은 데이터 정리:**
- Name: `received_name`, Value: `{{ $json.body.name }}`
- Name: `received_email`, Value: `{{ $json.body.email }}`
- Name: `received_message`, Value: `{{ $json.body.message }}`

---

## 실습 8 - Step 3: 조건 추가

Set 노드 오른쪽 **+** 클릭
→ IF 노드 추가

**긴급 여부 확인:**
- Value 1: `{{ $json.received_message }}`
- Operation: `Contains`
- Value 2: `긴급`

---

## 실습 8 - Step 4: 응답 메시지

**True** 출력: Set 노드
```
priority: 높음
response: 긴급 문의가 접수되었습니다. 즉시 처리하겠습니다.
```

**False** 출력: Set 노드
```
priority: 보통
response: 문의가 접수되었습니다. 순차적으로 처리하겠습니다.
```

---

## 실습 8 - Step 5: 웹훅 활성화

우측 상단:
1. **"Save"** 클릭 (꼭 저장!)
2. **"Active"** 토글 켜기

**이제 Webhook URL이 실제로 작동합니다**

---

## 실습 8 - Step 6: 테스트하기

**방법 1: 브라우저 개발자도구**
F12 → Console 탭:
```javascript
fetch('YOUR_WEBHOOK_URL', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({
    name: '홍길동',
    email: 'hong@test.com',
    message: '긴급 문의드립니다'
  })
})
```

**방법 2: Postman/Insomnia 사용**

---

## 실습 8 - Step 7: 실행 기록 확인

n8n 좌측 메뉴:
→ **"Executions"** 클릭
→ 방금 실행된 워크플로우 확인

**실제로 데이터가 들어와서 처리되었습니다!**

---

## 웹훅의 실전 활용

**구글 폼 → n8n**
- 고객 문의 접수 자동 처리

**결제 시스템 → n8n**
- 결제 완료 시 자동 작업

**자체 앱 → n8n**
- 커스텀 이벤트 처리

**다른 자동화 도구 → n8n**
- Zapier, Make.com 등과 연동

---

## 실습 9: 간단한 데이터베이스 연동
### Google Sheets 읽기

**목표**: 구글 시트에서 데이터 가져오기
**노드**: 2개 (Manual Trigger + Google Sheets)
**시간**: 20분

**실전에서 가장 많이 쓰는 조합!**

---

## 실습 9 - 준비: 구글 시트

**구글 스프레드시트 생성:**

| 이름 | 부서 | 이메일 |
|------|------|--------|
| 김철수 | 개발팀 | kim@test.com |
| 이영희 | 기획팀 | lee@test.com |
| 박민수 | 디자인팀 | park@test.com |

**시트 공유 설정:**
→ 링크가 있는 모든 사용자에게 공개

---

## 실습 9 - Step 1: 워크플로우 생성

새 워크플로우: `"실습9_구글시트읽기"`

1. Manual Trigger 추가
2. 오른쪽 **+** 클릭
3. `google sheets` 검색

---

## 실습 9 - Step 2: Credential 설정

**Google Sheets** 노드 선택 시:

1. **"Create New Credential"** 클릭
2. Google 계정으로 로그인
3. n8n 접근 권한 허용

**OAuth 인증 완료!**

---

## 실습 9 - Step 3: 시트 설정

**Resource**: `Sheet`
**Operation**: `Read`

**Document**: 
- 구글 시트 URL 붙여넣기

**Sheet Name**:
- `Sheet1` (또는 실제 시트 이름)

**Range**:
- `A1:C10` (데이터 범위)

---

## 실습 9 - Step 4: 실행

**Execute Workflow** 클릭
→ Google Sheets 노드 결과 확인

**구글 시트의 데이터가 n8n으로!**
```json
[
  {"이름": "김철수", "부서": "개발팀", "이메일": "kim@test.com"},
  {"이름": "이영희", "부서": "기획팀", "이메일": "lee@test.com"},
  ...
]
```

---

## 실습 10: 구글 시트에 데이터 쓰기
### Google Sheets Append

**목표**: 새로운 데이터를 시트에 추가
**노드**: 3개 (Manual + Set + Google Sheets)
**시간**: 15분

---

## 실습 10 - Step 1: 워크플로우

새 워크플로우: `"실습10_구글시트쓰기"`

1. Manual Trigger
2. Set 노드로 데이터 생성:
   - Name: `이름`, Value: `최지원`
   - Name: `부서`, Value: `마케팅팀`
   - Name: `이메일`, Value: `choi@test.com`

---

## 실습 10 - Step 2: Google Sheets 노드

**Operation**: `Append`

**Document**: 아까 만든 시트
**Sheet Name**: `Sheet1`

**Columns**: 
- `이름`
- `부서`
- `이메일`

---

## 실습 10 - Step 3: 실행 및 확인

**Execute Workflow** 클릭
→ 구글 시트로 가서 확인

**새로운 행이 자동으로 추가되었습니다!**

---

## 구글 시트의 활용

**데이터베이스 대용**
- 간단한 데이터 저장소
- 팀원들과 공유 쉬움

**실전 조합:**
- 웹훅 → 시트 저장
- 폼 제출 → 시트 기록
- 정기 리포트 → 시트 작성

**주의:** 대용량 데이터는 실제 DB 사용 권장

---

## 실습 11: 이메일 자동 발송
### Gmail 노드 사용하기

**목표**: 조건에 맞으면 이메일 보내기
**노드**: 4개 (Webhook + IF + Gmail + Set)
**시간**: 20분

**자동화의 꽃: 알림 발송!**

---

## 실습 11 - Step 1: 워크플로우 준비

새 워크플로우: `"실습11_이메일알림"`

**기본 구조:**
1. Webhook 트리거 (Path: `email-trigger`)
2. IF 노드 (금액 10만원 이상 확인)

---

## 실습 11 - Step 2: Gmail Credential

**Gmail** 노드 추가 시:

1. Credential 생성
2. Google 계정 로그인
3. 권한 허용

**보안 걱정?**
→ OAuth 방식이라 비밀번호 노출 없음
→ 언제든 권한 취소 가능

---

## 실습 11 - Step 3: 이메일 설정

**To**: `[본인 이메일]`
**Subject**: `금액 알림: 10만원 이상 거래 발생`
**Email Format**: `Text`
**Message**: 
```
안녕하세요,

10만원 이상의 거래가 발생했습니다.
금액: {{ $json.body.amount }}원
내용: {{ $json.body.description }}

확인 부탁드립니다.
```

---

## 실습 11 - Step 4: 테스트

Webhook으로 데이터 전송:
```json
{
  "amount": 150000,
  "description": "서비스 결제"
}
```

**이메일이 도착했나요?** 📧

---

## 이메일 자동화 주의사항

**스팸 방지:**
- 너무 자주 보내지 않기
- 수신자 동의 확보

**테스트:**
- 처음엔 본인 이메일로만
- 검증 후 실제 사용

**대안:**
- Slack, Discord (더 빠르고 편함)
- SMS (긴급한 경우)

---

## 실습 12: 슬랙 알림 보내기
### Slack 연동

**목표**: 구글 시트 업데이트 시 슬랙 알림
**노드**: 3개 (Google Sheets Trigger + Set + Slack)
**시간**: 20분

**팀 협업의 필수!**

---

## 실습 12 - 준비: 슬랙 워크스페이스

**필요한 것:**
- 슬랙 워크스페이스 (무료 가능)
- 테스트용 채널 생성
- 또는 자신에게 DM

**없으시면 Discord로 대체 가능**

---

## 실습 12 - Step 1: 워크플로우

새 워크플로우: `"실습12_슬랙알림"`

**Google Sheets Trigger** 추가:
- Event: `On Row Added`
- Document: 아까 만든 시트
- Sheet: `Sheet1`

**실행 간격**: 1분마다 확인

---

## 실습 12 - Step 2: 데이터 정리

Set 노드 추가:

```
message: 
새로운 팀원이 등록되었습니다!
- 이름: {{ $json.이름 }}
- 부서: {{ $json.부서 }}
- 이메일: {{ $json.이메일 }}
```

---

## 실습 12 - Step 3: Slack Credential

**Slack** 노드 추가:

1. Credential 생성
2. OAuth 인증
3. 워크스페이스 선택
4. 권한 허용

---

## 실습 12 - Step 4: 메시지 설정

**Resource**: `Message`
**Operation**: `Post`

**Channel**: 
- 채널 이름 또는 @사용자명

**Text**: 
```
{{ $json.message }}
```

**Attachments** (선택):
- 색상, 버튼 등 추가 가능

---

## 실습 12 - Step 5: 테스트

1. 워크플로우 **Active** 켜기
2. 구글 시트에 새 행 추가:
   - 이름: `신입사원`
   - 부서: `인사팀`
   - 이메일: `new@test.com`
3. 1분 대기
4. 슬랙 확인

**알림이 왔나요?** 🎉

---

## Google Sheets Trigger 작동 방식

**Polling (폴링) 방식:**
- n8n이 주기적으로 시트 확인
- 변경사항 발견 시 워크플로우 실행

**주의:**
- 실시간은 아님 (1분 간격)
- 여러 행 동시 추가 → 각각 실행

**실시간 필요하면:**
→ Webhook 사용

---

## 지금까지의 여정 정리

**12개 실습 완료!**

✅ 기본 노드 사용법 (Set, Code)
✅ 조건 분기 (IF, Switch)
✅ API 호출 (HTTP Request)
✅ 웹훅 (외부 연동)
✅ 구글 시트 (읽기/쓰기/트리거)
✅ 이메일 (Gmail)
✅ 슬랙 (알림)

**이제 거의 모든 자동화를 만들 수 있습니다!**

---

## 휴식 (10분)

---

## n8n 템플릿 라이브러리 탐색

**1,000개 이상의 완성된 자동화**

- 실무에서 검증된 패턴
- 복사해서 바로 사용
- 학습 자료로도 좋음

**함께 둘러봅시다**: n8n.io/workflows

---

## 템플릿 카테고리

**인기 카테고리:**
- 📧 Communication (이메일, 슬랙)
- 📊 Productivity (구글 워크스페이스)
- 💬 Social Media (SNS 자동화)
- 🤖 AI & ML (ChatGPT 연동)
- 📈 Sales & CRM (고객 관리)
- 🎯 Marketing (마케팅 자동화)

---

## 추천 템플릿 - 초급자용

**1. Notion Database Backup to Google Sheets**
- 노션 데이터를 정기적으로 백업

**2. RSS Feed to Slack**
- 블로그 새 글 → 슬랙 알림

**3. Form to Multiple Destinations**
- 폼 제출 → 시트 저장 + 알림

**4. Daily Weather Report**
- 매일 날씨 리포트 이메일

---

## 템플릿 사용법

1. 템플릿 페이지에서 **"Use Workflow"** 클릭
2. n8n에서 **"Import from URL"** 선택
3. URL 붙여넣기
4. Credential 설정 (필요시)
5. 테스트 실행
6. 내 상황에 맞게 수정

---

## 실습 13: 템플릿 가져와서 수정하기

**각자 실습 (30분):**

1. n8n.io/workflows 에서 관심있는 템플릿 찾기
2. 내 n8n에 가져오기
3. 실행해보고 어떻게 동작하는지 분석
4. 내 상황에 맞게 수정해보기

**강사가 돌아다니며 도와드립니다!**

---

## 자유 실습 시간 (30분)

**하고 싶은 것 선택:**

**Option 1**: 오늘 배운 내용 복습
**Option 2**: 더 많은 템플릿 탐색
**Option 3**: 자신의 업무 자동화 만들어보기

**질문 환영합니다!**

---

## 내 업무 자동화 아이디어 찾기

**질문 리스트:**

- 매일/매주 반복하는 작업은?
- 여러 앱을 오가며 하는 일은?
- 데이터를 복사-붙여넣기 하는 작업은?
- "이게 자동이면 좋겠다" 싶은 것은?
- 팀원에게 자주 알려줘야 하는 정보는?

**종이에 3개 이상 적어보세요!**

---

## 자동화 가능성 판단

**자동화하기 좋음:**
- ✅ 규칙이 명확함
- ✅ 자주 반복됨
- ✅ 데이터 기반
- ✅ 여러 단계 있음

**자동화 어려움:**
- ❌ 매번 다른 판단 필요
- ❌ 창의성/감성 중요
- ❌ 규칙이 모호함

---

## 자동화 시작하기 팁

**시작은 작게:**
- 간단한 것부터 (2-3개 노드)
- 한 번에 하나씩
- 성공 경험 쌓기

**점진적 확장:**
- 작동하면 기능 추가
- 조건 추가
- 다른 앱 연결

**완벽하지 않아도 OK!**

---

## 흔한 에러와 해결법

**"Credentials invalid"**
→ Credential 재인증

**"Node not found"**
→ 노드 이름 오타 확인

**"Expression error"**
→ {{ }} 표현식 확인, 데이터 구조 점검

**"Rate limit exceeded"**
→ API 호출 횟수 제한, 간격 늘리기

---

## 디버깅 팁

**데이터 흐름 확인:**
- 각 노드를 클릭해서 Input/Output 확인
- 문제 있는 노드 앞에 Set 노드 추가

**테스트 방법:**
- Manual Trigger로 수동 테스트
- 작은 데이터셋으로 먼저

**에러 메시지:**
- 자세히 읽기
- 구글/ChatGPT에 검색

---

## 오늘 배운 내용 총정리

**핵심 개념:**
- 워크플로우, 노드, 트리거
- 데이터 흐름과 표현식 {{ }}

**실습한 노드들:**
- Manual Trigger, Schedule Trigger, Webhook
- Set, Code, IF, Switch
- HTTP Request (API)
- Google Sheets, Gmail, Slack

**12개 워크플로우 직접 제작!**

---

## 주요 패턴 요약

**1. 정기 작업**
```
[Schedule] → [작업] → [알림]
```

**2. 외부 연동**
```
[Webhook] → [처리] → [저장/알림]
```

**3. 조건부 처리**
```
[트리거] → [IF] → [분기 처리]
```

**4. 데이터 파이프라인**
```
[소스] → [변형] → [목적지]
```

---

## 실전 활용 시나리오

**고객 지원:**
- 문의 접수 → 분류 → 담당자 배정

**마케팅:**
- 이벤트 참가 → CRM 저장 → 감사 메일

**프로젝트 관리:**
- 이슈 생성 → 슬랙 알림 → 스프레드시트 기록

**데이터 수집:**
- 웹 크롤링 → 데이터 정리 → DB 저장

---

## 다음 단계 학습 로드맵

**초급 다음:**
- 더 많은 앱 연동 (Notion, Airtable, Discord)
- 복잡한 데이터 변형
- 에러 처리 (Error Workflow)
- 서브 워크플로우

**중급:**
- Database 직접 연결
- Custom API 만들기
- 대용량 데이터 처리
- 성능 최적화

---

## 유용한 리소스

**공식 문서**
- docs.n8n.io
- 각 노드별 상세 설명

**커뮤니티**
- community.n8n.io
- 질문/답변, 팁 공유

**YouTube**
- n8n 공식 채널
- 단계별 튜토리얼

**템플릿**
- n8n.io/workflows
- 실전 예제

---

## 숙제 (선택사항)

**다음 시간까지:**

1. 오늘 만든 워크플로우 중 1개를 실제로 사용해보기
2. 템플릿 2개 이상 가져와서 분석
3. 자신의 업무 자동화 아이디어 3개 구체화
4. 가능하면 간단한 자동화 1개 완성

**다음 시간에 공유해봅시다!**

---

## Day 2 미리보기

**실전 자동화 완성:**

- 실제 업무 사례 기반
- 여러 서비스 연결
- 복잡한 로직 구현
- 에러 처리 방법
- 나만의 자동화 프로젝트

**더 고급진 자동화를 만들 것입니다!**

---

## 오늘의 성취

**여러분이 해낸 것:**

✨ 12개의 워크플로우 직접 제작
✨ API, 구글 시트, 이메일, 슬랙 연동
✨ 조건부 로직 구현
✨ 템플릿 활용법 습득
✨ 자동화의 기본 원리 이해

**자신감을 가지세요!**

---

## Q&A

**질문 있으신가요?**

- 오늘 배운 내용
- 막혔던 부분
- 자동화 아이디어 검증
- 다음 시간 궁금한 점

---

## 피드백 부탁드립니다

**간단한 설문:**

1. 오늘 강의 속도는? (빠름/적당/느림)
2. 어려웠던 부분은?
3. 더 알고 싶은 내용은?
4. 실습 시간은 충분했나요?
5. 다음 시간 기대사항은?

**여러분의 의견이 강의를 개선합니다!**

---

## 마무리

**오늘 정말 수고하셨습니다!** 🎉

처음엔 낯설었던 n8n,
이제는 기본적인 자동화를 만들 수 있게 되었습니다.

**집에 가서 꼭 한 번 더 만져보세요.**
반복이 실력을 만듭니다.

**다음 시간에 또 만나요!**

---

## 연락처 & 지원

**강사 이메일:** [이메일 주소]
**슬랙/카톡 채널:** [링크]

**강의 자료:**
- 슬라이드: [다운로드 링크]
- 예제 워크플로우: [공유 링크]
- 추가 자료: [구글 드라이브]

**언제든 질문하세요!**
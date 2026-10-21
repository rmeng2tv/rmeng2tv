## 안녕하세요, 김보수(rmeng2)입니다

현장 업무를 시스템으로 바꾸는 1인 개발자입니다.
고객사의 CRM, 리드 수집 사이트, 업무 자동화를 **설계부터 배포·운영까지** 직접 맡고 있습니다.

- 업무 웹앱: 고객·접수·견적·정산·알림톡까지 이어지는 운영 CRM
- 자체 서비스: 멀티테넌트 SaaS, 무료 견적서 생성기(웹 + 토스 미니앱)
- 지역 SEO: 지역×서비스 리드 사이트 자체 사업 운영
- 자동화: Python 도구, 구글 앱스 스크립트, 외부 크론 기반 배치 작업

## 대표 작업

> 회사·고객사 코드는 계약과 개인정보 보호를 위해 비공개입니다. 아래는 고객 정보를 뺀 사례 요약입니다.

### 1. 현장 서비스 업체 운영 CRM (운영 중)
- **문제**: 접수, 견적, 파트너 배정, 정산, 세금서류가 엑셀·메신저로 흩어져 있었음
- **설계**: 관리자·파트너 포털·고객 공개 열람으로 입구를 나누고, 견적서·완료보고서 PDF, 카카오 알림톡, 세금계산서 발행을 한 시스템으로 연결
- **포인트**: 파트너에게 단가·마진이 보이지 않도록 응답 단위에서 권한 분리, 이미 발송한 링크 토큰은 바뀌지 않게 설계
- `PHP` `MySQL` `Vanilla JS` `바로빌 SOAP` `Resend` `jsPDF`

### 2. 교육 기업 고객 퍼널 CRM (운영 중)
- **문제**: 리드, 고객, 캠페인, 클래스, 진단검사, 뉴스레터 데이터가 도구마다 따로 있었음
- **설계**: 고객 중복 판정을 공통 함수 하나로 통일, 역할 기반 권한 + 사람별 예외를 한 곳에서 계산, 대량 메일은 큐로 나눠 발송
- **포인트**: 공유 호스팅 제약을 외부 크론과 일회성 마이그레이션 패턴으로 우회, 광고 성과(Meta Insights)를 매일 DB로 동기화
- `PHP` `MySQL` `알림톡` `SMTP` `Meta Marketing API`

### 3. 멀티테넌트 업무 SaaS (자체 개발 중)
- 운영 CRM을 여러 업종이 함께 쓰는 SaaS로 새로 설계
- 한 DB + `company_id`, 모든 조회·저장이 **단일 관문**을 거쳐 회사 조건이 빠지면 에러가 나는 구조
- 4단계 계정 위계, 단독 설치 모드 스위치, GitHub Actions 자동 배포 + 자동 마이그레이션
- `PHP 8.2` `MySQL` `GitHub Actions` `Cloudflare`

### 4. 알맹이툴즈 견적서 생성기 (라이브)
- 로그인 없이 쓰는 4단계 견적서 위저드, 실시간 A4 미리보기, PDF·이미지 저장
- 한 코드베이스로 **웹과 토스 앱인토스 미니앱** 두 결과물을 빌드
- [tools.rmeng2.co.kr](https://tools.rmeng2.co.kr/) · `React 19` `Vite` `GitHub Actions`

### 5. AI 마케팅 글 생성 SaaS (개발 총괄, 라이브 후 인계)
- Claude·Gemini API로 SNS·블로그 글과 이미지 생성, Threads 공식 API 연동과 성과 조회, 크레딧 차감, AI 원가 로깅
- 외부 토큰 AES-256-GCM 암호화 저장, 인증 메일 도메인 인증(DKIM·SPF·DMARC)
- `Next.js` `TypeScript` `Supabase` `Vercel` `Claude API`

## 일하는 방식
- **구조 먼저**: 데이터 구조와 폴더 구조를 확정한 뒤 코드를 씁니다
- **보안 기본값**: 비밀값은 코드와 Git 밖에, 검증과 권한 확인은 서버에서, SQL은 prepared statement
- **실패를 전제로 한 연동**: 타임아웃, 재시도, 중복 발송 방지(멱등성), 실패 로그
- **지식 축적**: 현장에서 겪은 함정과 기술 결정을 개인 지식 저장소에 기록 (playbook 76개, ADR 3개)

## 기술 스택
| 분야 | 사용 |
|---|---|
| 백엔드 | PHP, MySQL·MariaDB, Supabase(PostgreSQL), Cloudflare Workers |
| 프론트엔드 | Vanilla JS, React, TypeScript, Next.js, Vite, Astro |
| 자동화 | Python, Google Apps Script, GitHub Actions |
| 인프라 | 카페24, FastComet(cPanel), Vercel, Cloudflare, GitHub Pages |
| 연동 | 카카오 알림톡(바로빌), 세금계산서, Resend, Meta·Threads API, Claude·Gemini API |
| CMS | WordPress (GeneratePress, Elementor, Astra) |

## About me (English)
Solo full-stack developer based in Seoul. I design, build, deploy, and operate business systems end to end: CRMs for field-service and education companies, a multi-tenant SaaS, local SEO lead sites, and AI-powered content tools. Most client work is private; the summaries above describe the problems and designs without client data.

## 연락
- 카카오톡 채널 [@알맹이컴퍼니](https://pf.kakao.com/_epaxbn/chat)
- 서비스 제안 페이지: [rmeng2tv.github.io/proposals](https://rmeng2tv.github.io/proposals/)

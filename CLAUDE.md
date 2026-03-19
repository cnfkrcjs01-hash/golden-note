# 김비서 프로젝트 지침

## 프로젝트 개요
- 단일 HTML 파일(index.html) 기반 업무 자동화 웹앱
- 로컬 실행 (python -m http.server 8080)
- GitHub: https://github.com/cnfkrcjs01-hash/golden-note.git

## 핵심 기능
1. 피복비 대상자 선별 (엑셀 업로드 → 5가지 기준 자동 판정)
2. 문서 배포 (계열사 자동 매핑 → 분할 → Gmail 발송)
3. 급여 품의서 자동 생성 (docxtemplater 템플릿)
4. 스케줄러 (Google Calendar API 연동)

## 기술 스택
- SheetJS, Tailwind CSS, Phosphor Icons (Duotone)
- Google Calendar API + Gmail API (OAuth 2.0)
- docxtemplater + PizZip (품의서)
- Web Worker (대용량 파싱)
- IndexedDB (파일 로컬 저장)

## 계열사 코드
OK, OKH, OC, OKAX, AFI, ACI, OKIP, ON, OT, EX

## 디자인
- Claude 스타일: 크림 배경(#F5F1EB), 테라코타 악센트(#C96442), 다크 브라운 사이드바(#2D2117)

## 주의사항
- 실제 파일의 컬럼명이 다양하므로 3단계 매칭 로직 사용 (정확일치→포함→역포함)
- 휴직 판정은 휴직종료일 기준 (시작일 아님)
- 대용량 엑셀은 Web Worker로 파싱 (UI 블로킹 방지)

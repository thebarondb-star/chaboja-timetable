# CHABOJA 타임테이블 프로젝트

## 프로젝트 개요
- **파일**: `index.html` (단일 파일, 순수 HTML/JS)
- **DB**: Supabase (`tt_phases`, `tt_tasks`, `tt_settings` 테이블)
- **배포**: Vercel 자동배포 (main 브랜치 push 시 자동)
- **로컬 확인**: `file:///C:/Users/user/chaboja-timetable/index.html` 브라우저에서 직접 열기
- **모바일 확인**: F12 → Ctrl+Shift+M (크롬 DevTools)

## Git 배포 규칙
- **레포**: `thebarondb-star/chaboja-timetable`
- **계정**: `thebarondb-star` (thebaronpro 계정으로는 push 불가 → 403)
- **배포**: `git push origin main` → Vercel 자동배포
- **명령어**:
  - "깃 저장" → commit + push origin main
  - "배포해줘" → 동일 (main이 곧 배포)

## 기술 스택
- 순수 HTML + CSS + JavaScript (프레임워크 없음)
- Supabase JS SDK (`cdn.jsdelivr.net/npm/@supabase/supabase-js@2`)
- SortableJS (`cdn.jsdelivr.net/npm/sortablejs@1.15.3`)
- 다크/라이트 모드 (`localStorage` 기반, 기본값 라이트)

## Supabase 연결 정보
```javascript
const SUPABASE_URL = 'https://sktfscayhmyiztgjzsde.supabase.co'
const SUPABASE_KEY = 'sb_publishable_9oZp0It0Nx4zd86JOYGKYQ_jMkuslhv'
```

## DB 스키마 (Supabase)
- `tt_settings`: 프로젝트 전체 설정 (name, start_date, end_date)
- `tt_phases`: 페이즈 목록 (title, gradient, sort_order, start_date, end_date)
- `tt_tasks`: 작업 목록 (phase_id, task_num, title, assignee, status, start_date, end_date, week_bars, subtasks, note, priority)

## 주요 기능
- 페이즈별 작업 관리 (드래그로 순서 변경)
- 간트차트 (주간 바 클릭으로 상태 변경, 날짜 입력 시 자동 채색)
- 세부작업 체크리스트 (완료 시 뱃지, 전체 완료 시 타이틀 완료 표시)
- 진행률 = 완료 세부작업 / 전체 세부작업
- 페이즈별 진행 요약바 (실시간)
- 대시보드 카드 클릭 시 세부작업 필터 목록
- 모바일 반응형 (768px 이하: 간트 숨김, 세부작업 2열 그리드)

## 담당자
- 이윤희 (나), 이순구 (개발자), 공동

## CSS 규칙
- 모든 CSS는 index.html 내 `<style>` 태그에 작성 (단일 파일)
- CSS 변수로 다크/라이트 모드 분기 (`--bg`, `--text` 등)

## 작업 이어가기
새 대화창에서 "프로젝트 확인해" 하면 이 파일 기반으로 바로 이어서 작업 가능.

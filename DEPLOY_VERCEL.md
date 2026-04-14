# 베리어프리 지도 수집 페이지 Vercel 배포 가이드

## 1) 로컬 점검
- 프로젝트 루트에 `index.html`이 있는지 확인
- 브라우저에서 `index.html` 실행 후 아래 항목 점검
  - 위치 권한 허용 시 지도/마커/좌표 표시
  - 지도 탭 시 마커 이동 및 좌표 갱신
  - 저장 버튼 클릭 시 개수 증가 및 localStorage 저장
  - CSV 다운로드 버튼 동작
  - 초기화 버튼 동작

## 2) GitHub에 업로드 (권장)
Vercel은 GitHub 연동 배포가 가장 간단합니다.

1. GitHub에서 새 저장소 생성
2. 현재 프로젝트(`index.html`, `DEPLOY_VERCEL.md`)를 푸시

## 3) Vercel 배포
1. [Vercel](https://vercel.com/) 로그인
2. `Add New...` > `Project`
3. GitHub 저장소 선택 후 `Import`
4. Framework Preset은 `Other` 또는 자동 감지값 사용
5. Build Command 비움, Output Directory 비움 (정적 단일 파일)
6. `Deploy` 클릭

배포 완료 후 발급된 URL로 접속합니다.

## 4) 모바일 실기기 최종 점검
- HTTPS URL로 접속되는지 확인 (위치 권한 필수)
- 첫 진입 시 권한 안내 모달 노출 여부
- 권한 거부 후 재요청 버튼 동작 여부
- 좌표/지도/폼/저장/CSV/초기화 전체 플로우 확인

## 5) 운영 팁
- 현재 데이터는 브라우저 `localStorage`에만 저장됩니다.
- 다른 기기와 데이터 동기화가 필요하면 추후 백엔드 API 연동이 필요합니다.

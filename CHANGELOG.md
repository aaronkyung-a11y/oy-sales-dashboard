# 올리브영 매출 대시보드 (aaronkyung-a11y/oy-sales-dashboard) — CHANGELOG

## fix-upload-range — 2026-10-26
- [버그] 파일 업로드 후 기간(dateFrom/dateTo)을 다시 계산하지 않아, 업로드 전 데이터 기준 '최근 7일'(예: 10/12~10/18)로
  필터가 고정됨 → '최근 7일' 상품별 매출이 0으로 계산되어 성장률·매출액 성장 Top 3가 "없음", 하락 Worst 3가 전부 "→ 0만원"
- 수정: 업로드 후 `state.data` 갱신 + 현재 선택 기간으로 `setDateRange()` 재호출 (직접 지정 기간이면 유지)
- 검증: 인라인 스크립트 문법 통과, API 실데이터(마지막 10/25)로 카드 결과 재현
- 이전 파일: `index-v-before.html` (커밋 d252ba1, 2026-05-12)

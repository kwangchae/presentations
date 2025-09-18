---
theme: apple-basic
title: '동적 조명 로봇팔 시스템 - 개선된 정량지표'
titleTemplate: '%s - 캡스톤디자인'
info: |
  캡스톤디자인 Week 3 발표 자료 (개선안)
  제목: 동적 조명 로봇팔 시스템 정량지표 개선
  발표자: 캡스톤 팀
  일자: 2025-09-18
author: 캡스톤 팀
keywords: 로봇팔,조명,정량지표,개선안,평가반영
layout: center
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
export:
  format: pdf
  timeout: 30000
  dark: false
  withClicks: true
  withToc: false
fonts:
  sans: ['Noto Sans KR', 'Inter', 'ui-sans-serif', 'system-ui', 'sans-serif']
  serif: ['Noto Serif KR', 'ui-serif', 'Georgia', 'serif']
  mono: ['D2 Coding', 'Fira Code', 'ui-monospace', 'monospace']
server:
  host: true
  port: 3030
---

<link rel="stylesheet" href="style.css">

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&family=Noto+Serif+KR:wght@400;700&display=swap');

* {
  font-family: 'Noto Sans KR', 'Inter', ui-sans-serif, system-ui, sans-serif !important;
}
</style>

# <div class="mt-10"><span class="primary-bold">개선된 정량지표</span> 및 <span class="primary-bold">평가 반영</span></div>
<div class="mt-20 text-xl">캡돌+i</div>
<div class="mt-2 opacity-80">캡스톤디자인 / Week 3 - 개선안</div>
<div class="mt-2 opacity-60">2025-09-18</div>
<img src="/images/logo.png" alt="Capdol-Logo" class="abs-br opacity-100 w-50 h-auto m-5" />

---

# 평가 피드백 요약

<div class="space-y-4">
<v-clicks>

## 주요 개선 사항
<div class="box-primary">
<span class="primary-bold">정량지표 1</span>: 거리 기준(15cm) 분리 → <span class="secondary">속도 매칭 기반</span>으로 변경

<span class="primary-bold">정량지표 2+4</span>: 조명 점유율과 떨림 안정성 → <span class="secondary">통합 측정</span>

<span class="primary-bold">정량지표 3</span>: 시야 방해 → <span class="secondary">3가지 자세 시나리오</span> 추가
</div>

## 새로운 측정 도구
- **가속도 센서**: 떨림 정량화
- **속도 매칭**: 사람 손 속도 대비 로봇팔 추종 성능

</v-clicks>
</div>

---

# 개선된 정량지표 1: <span class="primary-bold">반응성</span> (간단 지표)

<div class="space-y-3">
<v-clicks>

## 기존 문제점
<div class="box-secondary">
<span class="secondary-bold">15cm 기준 분리</span>가 합리적이지 않음 → 실제 사용 패턴과 불일치
</div>

## 개선된 지표(간단)
- **인식 시간**: <span class="accent">0.2초 이하</span>
  - 정의: 손이 정지해 있다가 움직이기 시작한 시점(모션 온셋)부터 로봇팔이 움직이기 시작하는 시점까지의 시간
- **추종 정확도**: 위치 오차 5cm 이하로 유지된 시간 비율(%)

## 합격 기준(간단)
- 인식 시간 ≤ 0.2초
- 5cm 이하 유지율 ≥ 85%

</v-clicks>
</div>

---

# 통합 정량지표 2: <span class="primary-bold">조명 안정성</span>

<div class="space-y-3">
<v-clicks>

## 통합 이유
<div class="box-primary">
조명 점유율과 떨림 안정성은 모두 <span class="primary-bold">조명 품질</span>에 직접 영향
</div>

## 측정 방법(간단)
- **기준 밝기 정의**: 카메라 프레임 4개 모서리(좌상·우상·좌하·우하)의 평균 밝기
- **ROI 밝기**: 손끝 중심 5cm 반경, 기준밝기의 <span class="accent">150% 이상</span>이면 ‘밝음’ 판정
- **가속도 센서(떨림)**: 로봇팔 끝단에 부착, 임계값 초과(예: 0.5g) 시 ‘경고’로 집계

## 통합 기준(간단)
- **밝기 통과율**: ROI가 기준밝기 대비 <span class="accent">150% 이상</span>인 시간 비율 <span class="accent">≥ 95%</span>
- **떨림 경고율**: 가속도 임계값(예: 0.5g) 초과 시간 비율 <span class="accent">≤ 5%</span>

</v-clicks>
</div>

---

# 개선된 정량지표 3: <span class="primary-bold">시야 방해율</span>

<div class="space-y-3">
<v-clicks>

## 3가지 자세 시나리오(정의·측정 기준 포함)

### 자세 1: <span class="secondary">머리 전방 숙임(20–30°)</span>
- 문제: 로봇팔이 머리 전방을 스치거나 충돌 위험
- 측정: 머리–로봇팔 최소거리 <span class="accent">＜ 15cm</span> 시 위험, 경로 예측 1초 내 침범 시 경고

### 자세 2: <span class="secondary">팔꿈치 90° 올림 + 몸 좌/우 20° 기울임</span>
- 문제: 팔꿈치/어깨와 로봇팔 간 간섭 및 시야 일부 차단
- 측정: 팔–로봇팔 최소거리, 차단 면적 비율 <span class="accent">＞ 10%</span> 시 방해

### 자세 3: <span class="secondary">손을 눈높이 이상으로 들기</span>
- 문제: 로봇팔이 얼굴 앞을 횡단하며 시야 차단 증가
- 측정: 시야 차단각 <span class="accent">＞ 30°</span> 또는 차단 시간 비율 <span class="accent">＞ 10%</span> 시 방해

## 통합 기준
각 자세별 5분 테스트, 위험/방해 시간 비율 <span class="accent">＜ 10%</span>, 충돌 0건

</v-clicks>
</div>

---

# 측정 방법 및 도구

<div class="space-y-4">
<v-clicks>

## 하드웨어
<div class="box-primary">
<span class="primary-bold">가속도 센서</span>: 로봇팔 끝단 부착 (떨림 측정)
<span class="primary-bold">고속 카메라</span>: 120fps 손 추적
<span class="primary-bold">조도 센서</span>: ROI 밝기 실시간 측정
</div>

## 소프트웨어
- **모션 온셋 감지**: 손 좌표 변화량이 문턱값(예: 3cm/s) 초과하는 첫 프레임
- **추종 정확도 계산**: 프레임별 손–광원 중심 거리 ≤ 5cm인 시간 비율
- **기준밝기 계산**: 프레임 4모서리 평균 밝기 산출(간단 평균)
- **충돌 감지**: 3D 최소거리 기반(간단 임계값)
- **시야 차단**: 눈–손–로봇팔 각도로 차단 여부만 판정(단순 임계값)

## 테스트 프로토콜
30분 실제 건담 조립, 속도 구간별(저속/중속/고속) 2분 씩, 3가지 자세 각 5분 별도 테스트

</v-clicks>
</div>

---

# 기대 효과 및 검증 계획

<div class="space-y-4">
<v-clicks>

## 개선 효과
<div class="box-secondary">
<span class="secondary-bold">더 정확한 성능 평가</span>: 실제 사용 패턴 반영
<span class="secondary-bold">안전성 강화</span>: 다양한 자세에서의 충돌 위험 사전 검증
<span class="secondary-bold">사용자 경험</span>: 자연스러운 작업 자세 허용
</div>

## 검증 일정
- **1주차**: 하드웨어 센서 통합
- **2주차**: 3가지 자세 시나리오 테스트
- **3주차**: 속도 매칭 알고리즘 최적화
- **4주차**: 통합 성능 검증

## 성공 기준
모든 정량지표를 동시에 만족하는 <span class="accent">통합 점수 85점 이상</span>

</v-clicks>
</div>

---
layout: center
class: text-center
---

<div class="pt-0">
  <span class="text-6xl">감사합니다!</span>
</div>

<div class="mt-10 opacity-80">
개선된 정량지표로 더 안전하고 정확한 시스템을 구현하겠습니다
</div>

---
theme: apple-basic
title: '동적 조명 로봇팔 시스템'
titleTemplate: '%s - 캡스톤디자인'
info: |
  캡스톤디자인 Week 3 발표 자료
  제목: 동적 조명 로봇팔 시스템 정량지표 설정
  발표자: 캡스톤 팀
  일자: 2025-09-17
author: 캡스톤 팀
keywords: 로봇팔,조명,정량지표,AI검토
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

# <div class="mt-10"><span class="primary-bold">정량지표 설정</span> 및 <span class="primary-bold"> AI 검토 기반 피드백</span></div>
<div class="mt-20 text-xl">캡돌+i</div>
<div class="mt-2 opacity-80">캡스톤디자인 / Week 3</div>
<div class="mt-2 opacity-60">2025-09-17</div>
<img src="/images/logo.png" alt="Capdol-Logo" class="abs-br opacity-100 w-50 h-auto m-5" />

---

# 프로젝트 개요

<div class="space-y-4">
<v-clicks>

## 문제 정의
<div class="box-primary">
<span class="primary-bold">건담 조립</span>시 미세 부품을 자세히 봐야 함 -> <span class="secondary">머리가 조명을 가려</span> 작업물에 그림자 발생 -> <span class="accent">가시성 저하, 집중도 및 정확도 하락</span>
</div>

## 해결 방안
- **2개의 카메라**로 손을 <span class="primary">실시간 인식</span>
- **동적 로봇팔**이 손을 따라가며 <span class="primary">조명 제공</span>
- **목표**: <span class="primary-bold">그림자 없이 항상 밝은 작업 시야</span>

</v-clicks>
</div>

---

# 정량지표 1: <span class="primary-bold">반응성</span> (이동속도)

<div class="space-y-3">
<v-clicks>

## 개요 (기존)
- **목적**: <span class="primary">작업 몰입 보장</span>을 위한 빠른 추종성
- **측정**: A->B 이동 시 반응 시간 + 이동 시간 (120fps)
- **기준**: <span class="secondary-bold">1초 이내 완료</span>(40cm/s 기준)


</v-clicks>
</div>

---

# 정량지표 1: <span class="secondary-bold">AI 검토 -> 개선</span>

<div class="space-y-3">
<v-clicks>

## 프롬프트
<div class="box-secondary">
"손 또는 프라모델 이동에 대해 조명이 늦지 않게 따라오는 성능을 정량화하려 합니다. 현실적인 기준과 측정법을 제안해 주세요."
</div>

## 인공지능 답변
- <span class="primary">소거리 이동 포함</span> 시나리오 권장, <span class="primary">인식</span>과 <span class="primary">이동</span>을 분리해 측정 권장
- <span class="primary">근거리와 원거리</span>의 별도 기준 제안, 시작과 완료 시점 정의 명확화 권장

## 개선된 지표
- **분리 지표**: 총 반응시간 = <code class="primary">인식지연</code> + <code class="secondary">이동시간</code>
- **시작점**: 손이 정지 -> 이동하는 시점
- **근거리(<= 15cm)**: <span class="accent">총 반응시간 &lt;= 0.30s</span>, 인식지연 <= 0.12s
- **원거리(> 15cm)**: <span class="accent">총 반응시간 &lt;= 1.00s</span>, 목표 평균 속도 >= 40cm/s

</v-clicks>
</div>

---

# 정량지표 2: <span class="primary-bold">조명 점유율</span>

<div class="space-y-3">
<v-clicks>

## 개요 (기존)
- **목적**: <span class="primary">세밀 작업</span>을 위해 작업물 상단이 항상 밝게 비춰져야 함
- **측정**: 실제 조립 30분 동안 마스킹 포인트 기준으로 조명 방향 측정
- **기준**: <span class="secondary-bold">95% 이상 점유</span> 시 성공


</v-clicks>
</div>

---

# 정량지표 2: <span class="secondary-bold">AI 검토 -> 개선</span>

<div class="space-y-3">
<v-clicks>

## 프롬프트
<div class="box-secondary">
"전문적인 장비없이 작업물이 충분히 밝게 비춰지는 시간을 정량화하려 합니다. 스마트폰/카메라만으로 가능한 측정법을 제안해 주세요."
</div>

## 인공지능 답변
- <span class="primary">ROI 밝기 기반 판정</span> 권장, 프레임 단위로 평균/중앙값 비교
- <span class="primary">상대밝기 임계값(0.3~0.45)</span> 활용, 연속 어두움 최대 길이 제한 권장

## 개선된 지표
- **ROI**: 손끝 중심 반경 5cm 원형 영역
- **기준 밝기**: 화면 4개 모서리 평균값 (그림자 영향 최소화) 
- **측정**: 프레임 단위 ROI 평균 밝기 <code class="primary">L_roi</code> / 기준 밝기 <code class="secondary">L_ref</code>
- **판정**: 상대밝기(L_roi/L_ref) >= 0.35 -> <span class="accent">"잘 비췄다"</span>
- **목표**: <span class="accent">0.5초 이상 어두우면 실패로 카운트</span>

</v-clicks>
</div>

---

# 정량지표 3: <span class="primary-bold">시야 방해율</span>

<div class="space-y-3">
<v-clicks>

## 개요 (기존)
- **목적**: <span class="primary">로봇팔/조명이 시야를 가려</span> 불편을 유발하는 문제 방지
- **측정**: 눈높이 카메라 영상에서 시야 노출/침범 프레임 비율 계산
- **기준**: <span class="secondary-bold">팔 침범 < 5%</span>, 시야 노출 < 2%


</v-clicks>
</div>

---

# 정량지표 3: <span class="secondary-bold">AI 검토 -> 개선</span>

<div class="space-y-3">
<v-clicks>

## 프롬프트
<div class="box-secondary">
"시야 방해율을 눈높이 카메라만으로 정량화하려 합니다. 시야각 관점의 더 자세한 정의, 연속 방해 허용치를 제안해 주세요."
</div>

## 인공지능 답변
- <span class="primary">작업자 아이 라인 기준 시야영역</span>을 다각형으로 정의하고, 로봇실루엣과의 교차 면적 비율로 방해 프레임 판정
- <span class="primary">연속 방해 최대 길이(0.3~0.5s)</span> 제한 권장, 근접 시 가중치 적용

## 개선된 지표
- **측정**: 눈과 ROI을 연결한 직선과 로봇팔 사이 최근접 거리
- **판정**: 거리 < 20cm -> 방해, < 10cm -> 심각한 방해
- **기준**: 방해 프레임 <- < 8%, 심각한 방해 < 2%

</v-clicks>
</div>

---

# 정량지표 4: <span class="primary-bold">떨림 안정성</span>

<div class="space-y-3">
<v-clicks>

## 개요 (기존)
- **목적**: <span class="primary">조명 흔들림으로 인한 그림자 떨림/피로 증가</span> 방지
- **측정**: 손의 미세 떨림(+/-5px) 유도 시 조명 떨림율 관찰
- **기준**: <span class="secondary-bold">10회 중 8회 이상</span> 로봇팔이 움직이지 않으면 통과


</v-clicks>
</div>

---

# 정량지표 4: <span class="secondary-bold">AI 검토 -> 개선</span>

<div class="space-y-3">
<v-clicks>

## 프롬프트
<div class="box-secondary">
"손의 미세 떨림에 로봇팔이 과도하게 반응하지 않도록 하는 성능을 정량화하려 합니다. 좌표 기반으로 간단히 측정할 수 있는 방법을 제안해 주세요."
</div>

## 인공지능 답변
- <span class="primary">좌표 기반 측정</span>으로 전문 장비 없이 간단한 분석 가능
- <span class="primary">False Trigger 분석</span>: 미세 떨림에 과도한 반응하는지 판단
- <span class="primary">정착 성능</span>: 손이 고정되었을 때 조명도 안정적으로 유지되는지 측정

## 개선된 지표
- **False Trigger Rate**: 손 +/-5mm 미세 이동 중 로봇팔 반응 비율 <span class="accent">&lt;= 10%</span>
- **정착 비율**: 손 고정 시 로봇팔이 +/-1cm 안에 머문 비율 <span class="accent">&gt;= 90%</span>
- **응답 필터**: <code class="primary">3mm 이상</code> 움직여야 로봇팔 반응 시작
- **미세 떨림**: 3초 윈도우에서 ±3mm 이내 변화
- **False Trigger**: 5% 이하
- **정착 기준**: 손 정지 후 2초간 로봇팔 ±5mm 이내
- **필터**: 연속 3프레임 이상 움직임만 반응
</v-clicks>
</div>

---
layout: center
class: text-center
---

<div class="pt-0">
  <span class="text-6xl">감사합니다!</span>
</div>

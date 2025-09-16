---
theme: apple-basic
title: '발표 제목'
titleTemplate: '%s - 랩미팅'
info: |
  대학원 랩미팅 발표 자료
  제목: 발표 제목
  발표자: 발표자명 · 소속
  일자: YYYY-MM-DD
author: 발표자명
keywords: keyword1,keyword2,keyword3
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
---

<link rel="stylesheet" href="/style.css">

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&family=Noto+Serif+KR:wght@400;700&display=swap');

* {
  font-family: 'Noto Sans KR', 'Inter', ui-sans-serif, system-ui, sans-serif !important;
}
</style>

# <span class="primary-bold">메인 키워드</span>를 활용한 <span class="primary-bold">연구 주제</span>
<span class="primary">핵심 방법론</span> 기반 <span class="primary">연구 목적</span>
<div class="mt-20 text-xl">발표자명</div>
<div class="mt-2 opacity-80">소속 · 학과</div>
<div class="mt-2 opacity-60">YYYY-MM-DD</div>
<img src="/images/lab_logo.png" alt="Lab Logo" class="abs-br opacity-80 w-24 h-auto m-6" />
---

# 목차
- 연구 배경·문제정의
- 연구목표·질문
- 연구 접근·아키텍처
- 실험 설계·방법론
- 기대기여·한계
- 진행상황·다음단계
---

# 연구 배경·문제정의

<div class="space-y-4">
<v-clicks>

기존 연구의 배경과 "<span class="primary-bold">핵심 키워드</span>를 활용한 <span class="primary-bold">연구 주제</span>" 설명

## 해결하려는 문제

- 문제점 1: <span class="primary">핵심 이슈</span> 설명
- 문제점 2: 기존 방법의 한계
- 문제점 3: 연구 공백 또는 필요성

## 제공하는 가치
- <span class="primary">기술적 기여</span> 설명
- <span class="primary">방법론적 기여</span> 설명
- <span class="primary">학술적 기여</span> 설명
</v-clicks>
</div>
---

# 연구 목표

<div class="space-y-1">
<v-clicks>

## 🎯 한 줄 목표
<span class="primary-bold">핵심 방법론</span>으로 <span class="primary">연구 대상</span>을 실시간 정량화하는 시스템

## 📋 구체적 연구 목표

### 1️⃣ <span class="primary-bold">핵심 방법론</span> 검증
- 구체적 목표 1 설명
- 신뢰성 있는 지표 확립

### 2️⃣ 실시간 분석 파이프라인
- <span class="primary">핵심 기술</span> 중심 분석 알고리즘 구축
- 실시간 처리 가능한 전처리 시스템

### 3️⃣ 평가 방법론
- 일반화 가능한 평가 프레임워크
- 주관적 평가 보완하는 <span class="primary">객관적 지표</span>

### 4️⃣ 통합 플랫폼 완성
- <span class="primary">시스템 구성요소</span> 동기화 시스템
- 다양한 시나리오 적용 가능한 범용 도구

</v-clicks>
</div>
---

# 핵심 연구질문

<div class="space-y-4">
<v-clicks>

## ❓ 주요 연구질문

### RQ1: 주요 변수 간 차이 🧠
실험 조건에서 <span class="primary">변수 A vs 변수 B</span> 간 <span class="primary-bold">측정 지표</span>의 차이는 유의한가?

**🔬 가설**: 조건 A에서 특정 지표 증가/감소 예상

### RQ2: 조작 변수의 영향 ⚖️
독립변수 조작이 <span class="primary">종속변수</span>에 미치는 영향은?

**🔬 가설**: 특정 조건에서 예상되는 반응

### RQ3: 환경 간 차이 🌐
<span class="primary">환경 A와 환경 B</span>에서 측정 지표의 차이는?

**🔬 가설**: 환경별 예상 차이점

</v-clicks>
</div>
---

# 연구 접근 전략

<div class="space-y-2">
<v-clicks>

## 연구 접근법의 핵심 아이디어

### 🔬 실험적 접근
- **객관적 측정**: 주관적 방법 → 객관적 지표
- **실시간 평가**: 실험 중 즉시 측정
- **정량적 분석**: 통계적 유의성 검증 가능한 데이터

### 🔄 순차적 확장 전략
- **1단계**: 시뮬레이션/제어된 환경에서 검증
- **2단계**: 실제 환경으로 점진적 확장
- **3단계**: 복잡한 환경으로 발전

### 🎯 과업 중심 설계
- **기본 과업**: 단순한 과업으로 시작
- **복잡도 증가**: 점진적 복잡성 증가
- **일반화**: 다양한 과업으로 확장

</v-clicks>
</div>
---

# 시스템 아키텍처

<div class="mt-25">

```mermaid {theme: 'neutral', scale: 0.42, fontFamily: 'Noto Sans KR'}
flowchart LR
    subgraph "📊 데이터 수집"
        Input["🔍 입력 시스템<br/>(데이터 측정)"]
        Stream["📡 스트리밍<br/>(실시간 전송)"]
        Process["💻 처리 시스템<br/>(신호 처리)"]
    end

    subgraph "🎮 실험 환경"
        Env["🎯 실험 환경<br/>(시각화/제어)"]
    end

    subgraph "🤖 제어 시스템"
        Control["⚙️ 제어 시스템<br/>(동작 제어)"]
    end

    subgraph "🔧 하드웨어"
        Hardware["🔧 하드웨어<br/>(물리적 구현)"]
    end

    subgraph "👤 참가자"
        User["👤 사용자<br/>(실험 참가자)"]
    end

    Input --> Stream
    Stream --> Process
    Process -.->|"🏷️ 이벤트 마커"| Env
    Env <-->|"🌐 통신<br/>명령/상태"| Control
    Control -->|"📊 제어 신호"| Hardware

    Env -.->|"👁️ 피드백"| User
    Hardware -.->|"🤝 상호작용"| User
    User -.->|"📊 데이터"| Input

    classDef inputStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef envStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef controlStyle fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef userStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px

    class Input,Stream,Process inputStyle
    class Env envStyle
    class Control,Hardware controlStyle
    class User userStyle
```
</div>
---

# 실험 설계·방법론

<div class="grid grid-cols-2 gap-8 items-start">
  <div class="space-y-3">
    <h3>🎯 실험 설계</h3>
    <h4>독립변수</h4>
    <v-clicks>
      <ul>
        <li><strong>변수 1</strong>: 조작 내용</li>
        <li><strong>변수 2</strong>: 조작 내용</li>
        <li><strong>변수 3</strong>: 조작 내용</li>
      </ul>
    </v-clicks>
    <h4>종속변수</h4>
    <v-clicks>
      <ul>
        <li><strong>측정 지표 1</strong>: 측정 방법</li>
        <li><strong>측정 지표 2</strong>: 측정 방법</li>
        <li><strong>측정 지표 3</strong>: 측정 방법</li>
      </ul>
    </v-clicks>
  </div>
  <div class="space-y-3">
    <h3>📋 실험 프로토콜</h3>
    <h4>참가자</h4>
    <v-clicks>
      <ul>
        <li><strong>표본 크기</strong>: N명</li>
        <li><strong>선정 기준</strong>: 포함/제외 기준</li>
        <li><strong>윤리 승인</strong>: IRB 승인 계획</li>
      </ul>
    </v-clicks>
    <h4>실험 절차</h4>
    <v-clicks>
      <ul>
        <li><strong>1단계</strong>: 사전 준비</li>
        <li><strong>2단계</strong>: 실험 진행</li>
        <li><strong>3단계</strong>: 사후 분석</li>
      </ul>
    </v-clicks>
  </div>
</div>
---

# 기대 기여

<div class="space-y-1">
<v-clicks>

## 🏆 방법론적 기여

### 📊 새로운 평가 패러다임
- <span class="primary">새로운 측정 방법</span> 방법론 확립
- 기존 방법 → <span class="primary">개선된 방법</span> 전환

### 🔬 정량화 기법 개발
- <span class="primary-bold">핵심 기법</span> 제시
- 실시간 처리 가능한 <span class="primary">분석 알고리즘</span>

## 🚀 실용적 기여

### 🗺️ 응용 가능성
- 다양한 분야 간 <span class="primary">적용 가능성</span>
- 확장성 및 일반화 가능성

### 📋 설계 가이드라인
- 관련 시스템 설계 시 활용 가능한 <span class="primary">가이드라인</span>
- 실무 적용을 위한 실시간 시스템

</v-clicks>
</div>
---

# 연구 리스크·완화

<div class="space-y-2">
<v-clicks>

## 주요 리스크
- 기술적 리스크: 구체적 위험 요소
- 실험적 리스크: 데이터 수집 관련 위험
- 시간적 리스크: 일정 지연 가능성
- 자원 리스크: 예산/장비 관련 위험

## 대응 전략
- 기술적 대응: 대안 기술/방법 준비
- 실험적 대응: 백업 계획 수립
- 일정 관리: 단계별 마일스톤 설정
- 자원 관리: 효율적 자원 활용 계획
</v-clicks>
</div>
---

# 연구 진행 현황

<div class="space-y-4">
<v-clicks>

## 현재 위치와 경과
- **현재 단계**: 구체적 진행 상황
- **완료 항목**: 이미 완료된 작업들
- **진행 중**: 현재 진행 중인 작업들

## 주요 성과
- 주요 성과 1: 구체적 결과
- 주요 성과 2: 달성된 목표
- 주요 성과 3: 검증된 내용

## 다음 단계 계획
- 단기 계획: 즉시 진행할 작업
- 중기 계획: 향후 몇 달 내 목표
- 장기 계획: 전체 연구 완성까지의 로드맵

</v-clicks>
</div>
---

# 데모 또는 결과

<div class="grid grid-cols-2 gap-2 mt-5">
  <v-clicks><img src="/images/demo1.png" alt="Demo 1" class="rounded shadow w-[640px] max-w-full" /></v-clicks>
  <v-clicks><img src="/images/demo2.png" alt="Demo 2" class="rounded shadow w-[640px] max-w-full" /></v-clicks>
</div>
---

# 영상 데모 (선택사항)
<video controls width="800" class="rounded shadow">
  <source src="/videos/demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
  <a href="/videos/demo.mp4">Download video</a>
</video>
---

# 다음 단계

<div class="space-y-2">
<v-clicks>

## 바로 다음 단계
- 단기 목표 1: 구체적 계획
- 단기 목표 2: 실행 방안

## 향후 계획
- 중기 목표: 몇 달 내 달성 목표
- 장기 목표: 최종 연구 완성 계획
- 확장 계획: 후속 연구 아이디어

## 협력 및 지원 요청
- 필요한 지원: 구체적 도움 요청
- 협력 가능성: 타 연구실과의 협력

</v-clicks>
</div>
---

# 하드웨어 사진 (선택사항)
<div class="grid grid-cols-3 gap-5 mt-5">
<v-clicks><img src="/images/hardware1.jpg" alt="Hardware 1" class="mt-6 rounded shadow w-[640px] max-w-full" /></v-clicks>
<v-clicks><img src="/images/hardware2.jpg" alt="Hardware 2" class="mt-6 rounded shadow w-[640px] max-w-full" /></v-clicks>
<v-clicks><img src="/images/hardware3.jpg" alt="Hardware 3" class="mt-6 rounded shadow w-[640px] max-w-full" /></v-clicks>
</div>
---

# 참고 문헌 (선택사항)
- 주요 참고문헌 1
- 주요 참고문헌 2
- 주요 참고문헌 3
- 관련 저장소: https://github.com/username/repository
---
layout: center
class: text-center
---

# 감사합니다! 🙏
# AR4 HRI 플랫폼 발표 자료

신뢰·작업부하 인지형 HRI 플랫폼에 대한 랩미팅 발표 자료입니다.

## 📁 파일 구조

```
ar4-presentation/
├── slide-content.md      # 📝 순수 콘텐츠 (편집용)
├── slides.md            # 🎯 Slidev 슬라이드 (자동 생성)
├── build-slides.py      # 🔨 빌드 스크립트
├── Makefile            # 📋 편의 명령어
├── public/
│   ├── style.css        # 🎨 스타일시트
│   └── images/         # 🖼️ 이미지 파일들
└── README.md           # 📖 이 파일
```

## 🚀 사용법

### 1. 콘텐츠 편집
`slide-content.md` 파일을 편집합니다. 이 파일은 순수한 마크다운 형식입니다.

### 2. 슬라이드 빌드
```bash
make build
# 또는
python3 build-slides.py
```

### 3. 개발 서버 실행
```bash
make dev
# 또는
npx slidev slides.md
```

### 4. PDF 내보내기
```bash
make export
# 또는
npx slidev export slides.md
```

## 🎨 스타일링

### 사용 가능한 CSS 클래스
- `primary-bold`: 주요 키워드 강조 (시안색)
- `underline-primary`: 중요한 문제점 밑줄
- `gradient-text`: 그라디언트 텍스트

### 자동 스타일링
빌드 스크립트가 다음 키워드들을 자동으로 스타일링합니다:
- EEG 바이오마커
- HRI 작업부하·신뢰 평가
- 신뢰·작업부하 인지형 HRI 플랫폼
- MoveIt 2
- 객관 지표 부족

## 📋 Makefile 명령어

```bash
make help          # 도움말 표시
make build         # 슬라이드 빌드
make dev           # 개발 서버 실행
make export        # PDF 내보내기
make clean         # 생성된 파일 정리
make watch         # 파일 변경 감시 (Linux/macOS)
```

## 🔄 워크플로우

1. **콘텐츠 작성**: `slide-content.md` 편집
2. **빌드**: `make build`로 `slides.md` 생성
3. **미리보기**: `make dev`로 실시간 확인
4. **내보내기**: `make export`로 PDF 생성

## 💡 장점

- **콘텐츠와 스타일 분리**: 내용에 집중할 수 있음
- **자동 스타일링**: 일관된 디자인 유지
- **버전 관리 친화적**: `slide-content.md`만 추적하면 됨
- **재사용성**: 다른 발표에서도 콘텐츠 재활용 가능

## 🎯 다음 단계

- [ ] 이미지/비디오 자동 포함 기능
- [ ] 테마 선택 옵션
- [ ] 다국어 지원
- [ ] 실시간 협업 기능
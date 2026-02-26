# NVA 데모 키오스크 — 사용 가이드

## 📁 폴더 구조

```
nva-kiosk/
├── index.html              ← 브라우저로 열면 됩니다
├── logo.png                ← Nota AI 로고 파일 (여기에 넣으세요)
├── README.md               ← 이 설명서
└── videos/                 ← 영상 파일 4개를 넣으세요
    ├── industrial-safety.mp4
    ├── surveillance.mp4
    ├── its.mp4
    └── dms.mp4
```

---

## 🚀 사용 방법 (3단계)

### Step 1: 파일 준비
- **로고**: `logo.png` 파일을 `nva-kiosk` 폴더에 넣기 (배경 투명 PNG 권장)
- **영상**: MP4 형식, 1920×1080 해상도 권장. 아래 파일명으로 `videos` 폴더에 넣기:
  - `industrial-safety.mp4` — 2인 1조 사다리 작업
  - `surveillance.mp4` — 쓰레기 무단 투기
  - `its.mp4` — Automatic Incident Detection
  - `dms.mp4` — Driver Monitoring System

### Step 2: 전시 현장 PC 세팅
1. `nva-kiosk` 폴더 전체를 USB에 복사
2. 전시 부스 PC에 복사
3. `index.html`을 **Chrome**으로 열기

### Step 3: 전체화면 실행
- **F11** 누르면 전체화면 (키오스크 모드)
- 다시 F11 누르면 해제

---

## ⚙️ 설정 변경

`index.html`을 메모장으로 열면 상단에 설정이 있습니다:

```javascript
const CONFIG = {
  videos: [
    'videos/industrial-safety.mp4',
    'videos/surveillance.mp4',
    'videos/its.mp4',
    'videos/dms.mp4',
  ],
  labels: ['Industrial Safety', 'Surveillance', 'ITS', 'DMS'],
  autoPlayDuration: 25,   // 자동 롤링 간격 (초)
  idleTimeout: 90,         // 클릭 후 자동 복귀 대기 (초)
};
```

---

## 💡 동작 요약

| 상태 | 동작 |
|------|------|
| AUTO | 25초마다 자동 전환 |
| 메뉴 클릭 | 해당 영상 고정 재생 |
| 90초 방치 | AUTO로 복귀 |

---

© 2021-2026. Nota Inc. All rights reserved.

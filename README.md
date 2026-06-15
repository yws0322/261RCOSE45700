# furniFit

가구 사진 한 장으로 3D 모델을 생성하고 AR로 공간에 배치해보는 iOS 앱입니다.  
VARCO 3D AI 엔진을 활용해 사진 업로드 → 3D 변환 → AR 공간 배치까지 원스톱으로 제공합니다.

## 주요 기능

- **3D 변환** — 가구 사진을 업로드하면 VARCO 3D가 GLB 모델 자동 생성
- **AR 공간 배치** — ARKit 기반으로 실제 공간에 여러 모델을 동시에 배치
- **갤러리** — 생성된 모델 검색·관리 (한국어 퍼지 검색 지원)
- **멀티뷰 업로드** — 단일 이미지 또는 다각도 이미지로 정밀도 향상
- **Color Grading** — 실제 조명 환경에 맞춘 색상 보정

## 기술 스택

| 파트 | 기술 |
|------|------|
| 클라이언트 | Flutter 3.x (iOS / Android) |
| AR | ARKit (iOS), arkit_plugin vendored fork |
| 3D 뷰어 | model_viewer_plus |
| AI 엔진 | VARCO 3D (KT) |
| 서버 | `server/` 참고 |

## 📂 폴더 구조

```
261RCOSE45700/
├── client/   # Flutter 앱 (iOS / Android)
└── server/   # 백엔드 API 서버
```

## 시작하기

### 클라이언트 실행

```bash
cd client
flutter pub get
flutter run
```

> Flutter 3.x 이상 필요. iOS 빌드는 Xcode 및 CocoaPods 설치 필요.

```bash
# iOS CocoaPods 설치 (최초 1회)
cd client/ios && pod install
```

### 서버 실행

```bash
cd server
# server/README.md 참고
```

## 환경 변수

`client/lib/config.dart` 에서 API 서버 주소를 설정합니다.

```dart
const String apiBaseUrl = 'https://your-api-server.com';
```

## 브랜치 전략

| 브랜치 | 용도 |
|--------|------|
| `main` | 배포 가능한 안정 코드 |
| `client/feat/...` | 클라이언트 기능 개발 |
| `server/feat/...` | 서버 기능 개발 |

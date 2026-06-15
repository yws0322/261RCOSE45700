# furniFit — Flutter 클라이언트

Flutter 기반 iOS/Android 앱입니다.

## 요구사항

- Flutter 3.x 이상
- Dart 3.x 이상
- iOS 빌드: Xcode 15+, CocoaPods

## 설치 및 실행

```bash
# 패키지 설치
flutter pub get

# iOS CocoaPods (최초 1회)
cd ios && pod install && cd ..

# 실행 (연결된 기기 또는 시뮬레이터)
flutter run
```

특정 기기 지정:
```bash
flutter devices          # 연결된 기기 목록 확인
flutter run -d <device-id>
```

## 코드 수정 반영

앱 실행 중 터미널에서:

| 키 | 동작 |
|---|---|
| `r` | Hot reload (UI 변경, 앱 상태 유지) |
| `R` | Hot restart (로직/상태 초기화) |
| `q` | 종료 |

## 주요 화면

| 화면 | 설명 |
|------|------|
| `auth_screen` | 로그인 / 회원가입 |
| `home_screen` | 홈 — 실제 모델 목록 및 카테고리 탭 |
| `upload_screen` | 사진 업로드 (단일 / 멀티뷰) |
| `processing_screen` | 3D 변환 진행 상태 폴링 |
| `result_screen` | 완성된 GLB 모델 뷰어 |
| `gallery_screen` | 전체 컬렉션 검색·관리 (한국어 퍼지 검색) |
| `ar_view_screen` | ARKit 기반 AR 공간 배치 |
| `model_url_screen` | 모델 URL 확인 및 공유 |

## 폴더 구조

```
lib/
├── main.dart
├── app.dart
├── api_client.dart       # 백엔드 API 통신
├── config.dart           # 서버 주소 설정
├── models/               # 데이터 모델
├── providers/            # 상태 관리 (Provider)
├── screens/              # 화면 위젯
├── theme/                # AppColors, AppTheme
└── widgets/              # FurniImage, GlbModelViewer
packages/
└── arkit_plugin/         # ARKit 플러그인 vendored fork
```

## 주요 패키지

| 패키지 | 용도 |
|--------|------|
| `arkit_plugin` (vendored) | iOS AR 공간 배치 |
| `model_viewer_plus` | GLB 3D 모델 뷰어 |
| `image_picker` | 갤러리 사진 선택 |
| `provider` | 상태 관리 |
| `http` | API 통신 |
| `google_fonts` | Nunito 폰트 |
| `path_provider` | GLB 파일 로컬 캐싱 |

## API 서버 설정

`lib/config.dart` 에서 서버 주소를 변경합니다.

```dart
const String apiBaseUrl = 'https://your-api-server.com';
```

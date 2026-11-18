# 가스등 도시 1851 (Gaslight City 1851)

빅토리아 시대 도시 꾸미기 게임. HTML 한 장으로 된 게임을 안드로이드 앱(WebView)에 담았다.

## 구조
| 경로 | 내용 |
|---|---|
| `GASLIGHT_CITY_vX.Y.Z.html` | 게임 판. 가장 높은 버전이 배포판 |
| `update.json` | 앱이 확인하는 최신판 정보(버전·파일·SHA-256). 새 HTML을 올리면 Actions가 자동 갱신 |
| `notes/vX.Y.Z.txt` | 업데이트 창에 뜨는 한 줄 설명(선택) |
| `android/` | 안드로이드 껍데기 앱 |

## 앱이 업데이트를 받는 방식
- 앱을 켤 때 최대 6시간에 한 번 `update.json`을 확인한다.
- 새 판이 있으면 업데이트 창 → 내려받아 SHA-256 검증 후 교체. **APK를 다시 설치할 필요 없음.**
- 즉시 확인: 안드로이드 **뒤로가기** → 「업데이트 확인」.
- 문제가 생기면 뒤로가기 → 「이전 버전 복구」(직전 판 하나를 보관).
- 인터넷이 없으면 지금 판 그대로 실행.
- 저장(도시)은 앱 안 저장소에 남아 업데이트해도 유지된다.

## APK 받기
- 저장소 **Releases → apk-latest → GaslightCity.apk** (휴대폰에서 바로 받기)
- 또는 Actions → Build Android APK → 최근 실행 → Artifacts
- 서명 키(`android/app/gaslight-sideload.keystore`)는 개인 설치용 고정 키. 같은 키라 덮어쓰기 설치가 된다. 스토어 배포용으로 쓰지 말 것.

## 새 판 내는 법
1. `GASLIGHT_CITY_v9.62.0.html`처럼 버전 이름으로 HTML을 올린다(선택: `notes/v9.62.0.txt`).
2. Actions가 `update.json`을 갱신한다. 끝.

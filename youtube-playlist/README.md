# 유튜브 플레이리스트 생성기

텍스트에서 유튜브 링크를 자동으로 추출하고 플레이리스트를 생성하는 웹 애플리케이션입니다.

## 🚀 데모

GitHub Pages에서 바로 사용해보세요: `https://[your-username].github.io/[repo-name]/youtube-playlist/`

## ✨ 기능

- 📝 텍스트에서 유튜브 링크 자동 추출
- 🔗 여러 링크 형식 지원 (youtube.com, youtu.be, shorts, embed)
- ✏️ 플레이리스트 이름 지정
- 🔐 Google OAuth 로그인
- 📱 반응형 디자인

## 📋 설정 방법

### 1. GitHub Pages 설정

1. 이 저장소를 GitHub에 생성
2. Settings > Pages로 이동
3. Source를 `main` 브랜치로 설정
4. 몇 분 후 `https://[your-username].github.io/[repo-name]/`에서 접속 가능

### 2. Google Cloud Console 설정

#### 2.1 프로젝트 생성
1. [Google Cloud Console](https://console.cloud.google.com/) 접속
2. 상단의 프로젝트 선택 > "새 프로젝트" 클릭
3. 프로젝트 이름 입력 (예: "YouTube Playlist Creator")
4. "만들기" 클릭

#### 2.2 YouTube Data API v3 활성화
1. 좌측 메뉴 > "API 및 서비스" > "라이브러리"
2. "YouTube Data API v3" 검색
3. "사용 설정" 클릭

#### 2.3 OAuth 동의 화면 구성
1. 좌측 메뉴 > "API 및 서비스" > "OAuth 동의 화면"
2. 사용자 유형: **외부** 선택
3. 앱 정보 입력:
   - 앱 이름: "YouTube Playlist Creator"
   - 사용자 지원 이메일: 본인 이메일
   - 개발자 연락처 정보: 본인 이메일
4. "저장 후 계속" 클릭
5. 범위 추가:
   - ".../auth/youtube" 선택
6. "저장 후 계속" 클릭
7. 테스트 사용자 추가 (본인 Gmail 추가)
8. "저장 후 계속" 클릭

#### 2.4 OAuth 2.0 클라이언트 ID 생성
1. 좌측 메뉴 > "API 및 서비스" > "사용자 인증 정보"
2. "사용자 인증 정보 만들기" > "OAuth 클라이언트 ID"
3. 애플리케이션 유형: **웹 애플리케이션**
4. 이름: "YouTube Playlist Web Client"
5. 승인된 JavaScript 원본:
   ```
   https://[your-username].github.io
   ```
6. 승인된 리디렉션 URI:
   ```
   https://[your-username].github.io/[repo-name]/youtube-playlist/
   ```
7. "만들기" 클릭
8. **클라이언트 ID를 복사** (예: `123456789-abcdefg.apps.googleusercontent.com`)

#### 2.5 코드에 클라이언트 ID 적용
1. `youtube-playlist/index.html` 파일 열기
2. 228번째 줄 근처의 다음 부분을 찾기:
   ```javascript
   client_id: 'YOUR_GOOGLE_CLIENT_ID',
   ```
3. `'YOUR_GOOGLE_CLIENT_ID'`를 복사한 클라이언트 ID로 교체:
   ```javascript
   client_id: '123456789-abcdefg.apps.googleusercontent.com',
   ```
4. 변경사항을 커밋하고 푸시

### 3. 테스트

1. GitHub Pages URL로 접속
2. "Google로 로그인" 버튼 클릭
3. Google 계정 선택 및 권한 승인
4. 유튜브 링크가 포함된 텍스트 붙여넣기
5. 플레이리스트 이름 입력
6. "플레이리스트 생성하기" 클릭
7. 본인의 YouTube 계정에서 플레이리스트 확인!

## 🔧 로컬 테스트

로컬에서 테스트하려면 웹 서버가 필요합니다:

```bash
# Python 3
python -m http.server 8000

# Node.js
npx http-server

# 브라우저에서 http://localhost:8000 접속
```

⚠️ 주의: 로컬 테스트를 위해서는 Google Cloud Console의 승인된 JavaScript 원본에 `http://localhost:8000`을 추가해야 합니다.

## 📝 사용 방법

1. 텍스트 입력창에 유튜브 링크가 포함된 텍스트 붙여넣기
2. 자동으로 추출된 링크 확인
3. 플레이리스트 이름 입력
4. Google 계정으로 로그인
5. "플레이리스트 생성하기" 클릭

## 🎯 지원하는 링크 형식

- `https://www.youtube.com/watch?v=...`
- `https://youtu.be/...`
- `https://www.youtube.com/shorts/...`
- `https://www.youtube.com/embed/...`

## ⚠️ 주의사항

- YouTube Data API에는 일일 할당량이 있습니다 (기본 10,000 units/day)
- 플레이리스트 생성: 50 units
- 동영상 추가: 50 units/video
- 따라서 하루에 약 100개의 동영상까지 추가 가능합니다

## 🐛 문제 해결

### "Google API가 로드되지 않았습니다" 오류
- 브라우저에서 서드파티 쿠키를 허용해야 합니다
- Chrome 설정 > 개인정보 및 보안 > 쿠키 및 기타 사이트 데이터

### "인증 실패" 오류
- OAuth 동의 화면에서 테스트 사용자로 추가되었는지 확인
- 클라이언트 ID가 올바르게 입력되었는지 확인
- JavaScript 원본과 리디렉션 URI가 정확한지 확인

### 플레이리스트가 생성되지 않음
- YouTube Data API v3가 활성화되어 있는지 확인
- API 할당량을 초과하지 않았는지 확인

## 📄 라이선스

MIT License

## 🤝 기여

이슈와 PR을 환영합니다!

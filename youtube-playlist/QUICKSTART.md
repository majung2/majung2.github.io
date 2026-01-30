# 빠른 시작 가이드

## 1단계: GitHub 저장소 생성 및 업로드

```bash
# 1. GitHub에서 새 저장소 생성 (예: my-web-tools)

# 2. 로컬에서 초기화
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/[your-username]/[repo-name].git
git push -u origin main
```

## 2단계: GitHub Pages 활성화

1. GitHub 저장소 페이지 접속
2. **Settings** 탭 클릭
3. 왼쪽 메뉴에서 **Pages** 클릭
4. Source를 **main** 브랜치로 선택
5. **Save** 클릭
6. 메인 페이지: `https://[your-username].github.io/[repo-name]/`
7. 유튜브 플레이리스트 생성기: `https://[your-username].github.io/[repo-name]/youtube-playlist/`

## 3단계: Google Cloud Console 설정 (자세한 내용은 README.md 참조)

### 간단 요약:
1. [Google Cloud Console](https://console.cloud.google.com/) 접속
2. 새 프로젝트 생성
3. YouTube Data API v3 활성화
4. OAuth 동의 화면 구성 (외부, 테스트 사용자 추가)
5. OAuth 클라이언트 ID 생성 (웹 애플리케이션)
   - JavaScript 원본: `https://[your-username].github.io`
   - 리디렉션 URI: `https://[your-username].github.io/[repo-name]/youtube-playlist/`
6. 클라이언트 ID 복사

## 4단계: 클라이언트 ID 설정

`youtube-playlist/index.html` 파일을 열고 228번째 줄 근처:

**변경 전:**
```javascript
client_id: 'YOUR_GOOGLE_CLIENT_ID',
```

**변경 후:**
```javascript
client_id: '123456789-abcdefg.apps.googleusercontent.com',
```

변경 후 커밋 & 푸시:
```bash
git add youtube-playlist/index.html
git commit -m "Add Google Client ID"
git push
```

## 5단계: 테스트!

1. `https://[your-username].github.io/[repo-name]/youtube-playlist/` 접속
2. Google로 로그인
3. 유튜브 링크 붙여넣기
4. 플레이리스트 생성!

---

## 문제가 있나요?

### 데모 모드로 먼저 테스트
- Google 로그인 없이도 링크 추출 기능은 바로 작동합니다
- "플레이리스트 생성하기" 버튼을 눌러보세요 (데모 모드)

### 로컬 테스트
```bash
# Python으로 간단한 서버 실행
python -m http.server 8000

# 브라우저에서 http://localhost:8000 접속
```

로컬 테스트 시 Google Cloud Console에 추가:
- JavaScript 원본: `http://localhost:8000`

---

더 자세한 내용은 `README.md`를 참조하세요!

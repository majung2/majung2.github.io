# 프로젝트 모음

다양한 웹 도구들을 모아놓은 저장소입니다.

## 🚀 GitHub Pages

이 페이지는 `https://majung2.github.io/`에서 확인할 수 있습니다.

## 📁 프로젝트 목록

### 1. [유튜브 플레이리스트 생성기](./youtube-playlist/)

텍스트에서 유튜브 링크를 자동으로 추출하고 플레이리스트를 생성하는 웹 애플리케이션

**기능:**
- 📝 텍스트에서 유튜브 링크 자동 추출
- 🔗 여러 링크 형식 지원
- ✏️ 플레이리스트 이름 지정
- 🔐 Google OAuth 로그인
- 📱 반응형 디자인

**접속:** `https://majung2.github.io/youtube-playlist/`

**자세한 설정 방법:** [youtube-playlist/README.md](./youtube-playlist/README.md)

---

## 🛠️ 사용 방법

### GitHub Pages 설정

1. 이 저장소를 GitHub에 업로드
2. Settings > Pages로 이동
3. Source를 `main` 브랜치로 설정
4. 몇 분 후 접속 가능

### 로컬 테스트

```bash
# Python
python -m http.server 8000

# Node.js
npx http-server

# 브라우저에서 http://localhost:8000 접속
```

## 📂 디렉토리 구조

```
.
├── index.html              # 메인 랜딩 페이지
├── README.md              # 이 파일
├── .gitignore
└── youtube-playlist/      # 유튜브 플레이리스트 생성기
    ├── index.html
    ├── README.md
    └── QUICKSTART.md
```

## 🔜 예정된 프로젝트

- 더 많은 유용한 도구들이 추가될 예정입니다!

## 📄 라이선스

MIT License

## 🤝 기여

이슈와 PR을 환영합니다!

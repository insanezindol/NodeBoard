# NodeBoard

Node.js와 Express를 사용하여 구축된 간단한 게시판 웹 애플리케이션입니다.

## 📝 프로젝트 소개

NodeBoard는 사용자가 글을 작성하고, 댓글을 달고, 파일을 업로드할 수 있는 기본적인 게시판 기능을 제공하는 웹 애플리케이션입니다. MongoDB를 데이터베이스로 사용하며, EJS 템플릿 엔진을 통해 동적인 웹 페이지를 생성합니다.

## 🚀 주요 기능

-   ✍️ **글 작성/수정/삭제**: 제목, 내용, 작성자 정보로 게시글 관리
-   💬 **댓글 시스템**: 각 게시글에 댓글 작성 및 관리
-   📁 **파일 업로드**: Multer를 사용한 파일 첨부 기능
-   👀 **조회수 관리**: 게시글별 조회수 자동 카운팅
-   🔒 **비밀번호 보호**: 게시글 수정/삭제 시 비밀번호 확인
-   📊 **게시글 히스토리**: 수정 내역 추적 및 관리

## 🛠 기술 스택

### Backend

-   **Node.js**: JavaScript 런타임 환경
-   **Express.js**: 웹 프레임워크
-   **MongoDB**: NoSQL 데이터베이스
-   **Mongoose**: MongoDB ODM

### Frontend

-   **EJS**: 템플릿 엔진
-   **HTML/CSS**: 마크업 및 스타일링

### 주요 라이브러리

-   **multer**: 파일 업로드 처리
-   **body-parser**: HTTP 요청 본문 파싱
-   **morgan**: HTTP 요청 로깅
-   **cookie-parser**: 쿠키 파싱

## 📂 프로젝트 구조

```
NodeBoard/
├── app.js                 # 메인 애플리케이션 파일
├── package.json          # 프로젝트 의존성 및 설정
├── models/               # 데이터베이스 모델
│   └── boardSchema.js   # 게시판 스키마 정의
├── routes/              # 라우팅 파일들
│   ├── index.js        # 메인 라우트
│   └── contents.js     # 게시판 관련 라우트
└── views/              # EJS 템플릿 파일들
    ├── index.ejs       # 메인 페이지
    ├── board.ejs       # 게시판 목록
    ├── boardDetail.ejs # 게시글 상세 페이지
    └── error.ejs       # 에러 페이지
```

## ⚙️ 설치 및 실행

### 필요 조건

-   Node.js (v12 이상 권장)
-   MongoDB 서버

### 설치 과정

1. **저장소 클론**

```bash
git clone <repository-url>
cd NodeBoard
```

2. **의존성 설치**

```bash
npm install
```

3. **MongoDB 설정**

-   MongoDB 서버가 실행 중인지 확인
-   `app.js`의 MongoDB 연결 설정을 본인 환경에 맞게 수정

4. **애플리케이션 실행**

```bash
npm start
```

5. **브라우저에서 확인**

-   `http://localhost:3000`에서 애플리케이션 확인

## 🗃️ 데이터베이스 스키마

### Board Collection

```javascript
{
  writer: String,        // 작성자명
  password: String,      // 게시글 비밀번호
  title: String,         // 게시글 제목
  contents: String,      // 게시글 내용
  comments: [{           // 댓글 배열
    name: String,        // 댓글 작성자
    memo: String,        // 댓글 내용
    date: Date          // 댓글 작성일
  }],
  count: Number,         // 조회수 (기본값: 0)
  date: Date,           // 작성일
  updated: [{           // 수정 히스토리
    title: String,
    contents: String,
    date: Date
  }],
  deleted: Boolean,     // 삭제 여부 (기본값: false)
  fileUp: [String]      // 업로드된 파일 경로들
}
```

## 📝 사용 방법

1. **게시글 작성**: 메인 페이지에서 새 글쓰기 버튼 클릭
2. **게시글 조회**: 게시판 목록에서 원하는 게시글 클릭
3. **댓글 작성**: 게시글 상세 페이지에서 댓글 입력
4. **파일 업로드**: 글 작성 시 파일 첨부 가능
5. **게시글 수정/삭제**: 비밀번호 입력 후 수정/삭제 가능

---

**NodeBoard** - Node.js 기반의 간단하고 실용적인 게시판 시스템

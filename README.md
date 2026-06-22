# CTManagement-app

**코딩 테스트 문제 관리**를 위한 단일 페이지 웹 애플리케이션입니다.  
문제 이름, 링크, 진행도를 등록·수정·삭제하고, 필터·검색·다크 모드를 지원합니다.  
데이터는 브라우저 `localStorage`에 저장됩니다.

## 주요 기능

- **문제 CRUD**: 이름, URL, 진행도(%) 추가·수정·삭제
- **진행도 필터**: 전체 / 미시작(0%) / 진행 중 / 완료(100%)
- **검색**: 문제 이름 키워드 검색
- **시각적 상태**: 진행도에 따른 카드 테두리 색상
  - 0%: 회색 | 1~99%: 주황 | 100%: 초록
- **다크 모드**: 테마 토글 + `localStorage` 저장
- **삭제 복원 없음**: 단순 로컬 관리 도구

## 기술 스택

| 구분 | 기술 |
|------|------|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Storage | localStorage (`problem` 키) |
| 배포 | 정적 파일 (서버 불필요) |

## 프로젝트 구조

```
CTManagement-app/
└── index.html    # UI + CSS + JavaScript (SPA)
```

## 실행 방법

별도 빌드·설치 없이 `index.html`을 브라우저에서 열면 됩니다.

```bash
# 예: Live Server 또는 파일 더블클릭
start index.html
```

## 사용 방법

1. **Home** 탭에서 문제 이름, 링크, 진행도(0~100) 입력 후 **추가**
2. **List** 탭에서 등록된 문제 카드 확인
3. **edit** → 폼에 값이 채워지면 수정 후 **수정** 버튼
4. **delete** → 해당 문제 삭제
5. **All / Not Started / Doing / Done** 필터로 상태별 보기
6. **search** 입력으로 이름 검색
7. **dark_mode**로 다크 테마 전환

## localStorage 데이터 형식

```json
[
  {
    "id": 1710000000000,
    "name": "백준 1000",
    "url": "https://www.acmicpc.net/problem/1000",
    "percent": "50"
  }
]
```

## 참고

- 브라우저·기기별로 데이터가 분리됩니다.
- 캐시/데이터 삭제 시 저장 내용이 사라질 수 있습니다.

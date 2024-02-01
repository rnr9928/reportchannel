# <div align="center">**CityLabs Front Repository**</div>

# env 파일 추가 front,admin 둘다 파일 생성하기

./admin/.env

```
PORT = 3001
REACT_APP_BASE_URL="http://localhost:8080"
REACT_APP_FABRIC_URL="http://localhost:8088"
```

./frontend/.env

```
PORT = 3000
REACT_APP_BASE_URL="http://localhost:8080"
REACT_APP_FABRIC_URL="http://localhost:8088"
```

## COMMIT CONVENTION

```
<type>(<scope>): <short summary>
  │       │          │
  │       │          └─⫸ 명령문, 현재 시제로 작성합니다. 대문자를 사용하지 않으며,마침표로 끝내지 않습니다.
  │       │
  │       └─⫸ Commit Scope: 어디가 변경되었는지 ex) rootScope,ngHref, ngClick
  │
  └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|test
```

### Commit Type 종류들

- feat : 새로운 기능 추가

- fix : 버그 수정

- docs : 문서 관련

- style : 스타일 변경 (포매팅 수정, 들여쓰기 추가, …)

- refactor : 코드 리팩토링

- test : 테스트 관련 코드

- build : 빌드 관련 파일 수정

- ci : CI 설정 파일 수정

- perf : 성능 개선

- chore : 그 외 자잘한 수정

## **Fork** 방법

1. 해당 레퍼지토리 fork (main branch 자동으로 생성)

2. fork한 레퍼지토리에서 개인 브랜치 만들기

3. 개인 브랜치에서 작업

## **Merge** 방법

- main 브런치 pull 방법

1. main브런치로 이동

2. 아래 그림 빨간 부분 클릭

   <img width="704" alt="pull" src="https://user-images.githubusercontent.com/107897812/211035976-53f8ec0b-205b-4954-843c-e17ff64d567a.png">

   <img width="704" alt="pull2" src="https://user-images.githubusercontent.com/107897812/211035981-6e1e8508-5f05-42c1-8168-4a5cc3d10113.png">

3. 터미널에 git pull 명령어 입력

   ```
   git pull
   ```

4. main브런치와 개인브런치 merge

   ```
   git merge seok
   ```

5. 오류 확인 후 정상인 경우 git push

   ```
   git push
   ```

6. push 후 아래 그림에 따라 pull request 처리

## pull request창 열기

   <img width="656" alt="pull3" src="https://user-images.githubusercontent.com/107897812/211038644-a75f9ac2-214b-467e-abfb-e63537f19fa6.png">

## pull request 내용 작성

    <img width="625" alt="pull4" src="https://user-images.githubusercontent.com/107897812/211038651-7bbb0112-76ea-45ea-a645-1b1a0f070846.png">

## fork해온 레퍼지토리의 main브런치와 merge

    <img width="668" alt="pull6" src="https://user-images.githubusercontent.com/107897812/211038661-58c71630-b4f2-49ff-9c95-88b2f1da6d7b.png">

    <img width="665" alt="pull7" src="https://user-images.githubusercontent.com/107897812/211038667-c04b4990-f1f9-49c6-b64f-3a6cb5df51e4.png">

```
citylabsFront
├─ .eslintrc.json
├─ .prettierrc.json
├─ admin
│  ├─ jsconfig.json
│  ├─ package-lock.json
│  ├─ package.json
│  ├─ public
│  │  └─ index.html
│  ├─ README.md
│  └─ src
│     ├─ App.jsx
│     ├─ App.test.js
│     ├─ assets
│     │  ├─ fonts
│     │  │  ├─ NotoSansKR-Light.otf
│     │  │  ├─ NotoSansKR-Medium.otf
│     │  │  └─ NotoSansKR-Regular.otf
│     │  └─ icons
│     │     ├─ cancel.svg
│     │     ├─ eye.svg
│     │     ├─ eye_close.svg
│     │     ├─ ic_add.svg
│     │     ├─ ic_back.svg
│     │     ├─ ic_close.svg
│     │     ├─ ic_del.svg
│     │     ├─ ic_del2.svg
│     │     ├─ ic_enter.svg
│     │     ├─ ic_link.svg
│     │     ├─ ic_login.svg
│     │     ├─ ic_logout.svg
│     │     ├─ ic_off.svg
│     │     ├─ ic_on.svg
│     │     ├─ ic_pic.svg
│     │     ├─ ic_reply.svg
│     │     ├─ ic_report.svg
│     │     ├─ ic_search.svg
│     │     ├─ ic_side.svg
│     │     ├─ left.svg
│     │     ├─ log_out.svg
│     │     ├─ menu.svg
│     │     ├─ right.svg
│     │     └─ support.svg
│     ├─ baseStyles
│     │  └─ index.js
│     ├─ components
│     │  ├─ buttons
│     │  │  └─ MoveBtn.jsx
│     │  ├─ comment
│     │  │  ├─ api
│     │  │  │  └─ api.js
│     │  │  ├─ Comment.js
│     │  │  └─ WriteSection.js
│     │  ├─ index.js
│     │  ├─ pagesContent
│     │  │  ├─ index.jsx
│     │  │  └─ styles.js
│     │  ├─ report
│     │  │  ├─ comment
│     │  │  │  ├─ deleteCommentBtn
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ eachComment
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  └─ registerCommentBtn
│     │  │  │     └─ index.jsx
│     │  │  ├─ dateRange
│     │  │  │  ├─ index.jsx
│     │  │  │  └─ style.css
│     │  │  ├─ guide
│     │  │  │  ├─ enrollBtn
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ list
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ pagination
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ search
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  └─ searchBtn
│     │  │  │     ├─ index.jsx
│     │  │  │     └─ styles.js
│     │  │  ├─ issue
│     │  │  │  ├─ excelBtn
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ list
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ pagination
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  ├─ search
│     │  │  │  │  ├─ index.jsx
│     │  │  │  │  └─ styles.js
│     │  │  │  └─ searchBtn
│     │  │  │     ├─ index.jsx
│     │  │  │     └─ styles.js
│     │  │  ├─ reportList
│     │  │  │  ├─ index.jsx
│     │  │  │  └─ styles.js
│     │  │  └─ reportSearchCondition
│     │  │     ├─ index.jsx
│     │  │     └─ styles.js
│     │  ├─ sideBar
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  └─ topBar
│     │     ├─ index.jsx
│     │     ├─ model.js
│     │     └─ styles.js
│     ├─ constants
│     │  ├─ contentConstant.js
│     │  ├─ logicConstant.js
│     │  ├─ pathConstant.js
│     │  ├─ p_labelConstance.js
│     │  └─ uiConstant.js
│     ├─ dummyData
│     │  └─ reportData_dummy.js
│     ├─ index.css
│     ├─ index.jsx
│     ├─ initCss.css
│     ├─ layouts
│     │  ├─ Layout.jsx
│     │  ├─ model.js
│     │  ├─ styles.js
│     │  └─ SubLayout.jsx
│     ├─ pages
│     │  ├─ issueBoardDetail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ issueBoardList
│     │  │  ├─ index.jsx
│     │  │  └─ styles.js
│     │  ├─ main
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ managementUserEdit
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportDetail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportGuide
│     │  │  ├─ index.jsx
│     │  │  └─ styles.js
│     │  ├─ reportGuideDetail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportGuideRegi
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportManagement
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ template
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  └─ userDetailEdit
│     │     ├─ index.jsx
│     │     ├─ model.js
│     │     └─ styles.js
│     ├─ router
│     │  └─ index.jsx
│     ├─ setupTests.js
│     ├─ store
│     │  ├─ configureStore.js
│     │  ├─ index.js
│     │  ├─ middleware
│     │  │  ├─ index.js
│     │  │  └─ reportCommentAction.js
│     │  └─ reducers
│     │     ├─ layoutReducer.js
│     │     ├─ modalReducer.js
│     │     ├─ reportCommentsReducer.js
│     │     ├─ rootReducer.js
│     │     ├─ toastReducer.js
│     │     └─ userReducer.js
│     └─ utils
│        ├─ index.js
│        └─ report
│           └─ detail
│              └─ index.js
├─ frontend
│  ├─ jsconfig.json
│  ├─ package-lock.json
│  ├─ package.json
│  ├─ public
│  │  └─ index.html
│  └─ src
│     ├─ App.jsx
│     ├─ App.test.js
│     ├─ assets
│     │  ├─ fonts
│     │  │  ├─ NotoSansKR-Light.otf
│     │  │  ├─ NotoSansKR-Medium.otf
│     │  │  └─ NotoSansKR-Regular.otf
│     │  └─ icons
│     │     ├─ cancel.svg
│     │     ├─ check.svg
│     │     ├─ eye.svg
│     │     ├─ eye_close.svg
│     │     ├─ ic_add.svg
│     │     ├─ ic_back.svg
│     │     ├─ ic_close.svg
│     │     ├─ ic_del.svg
│     │     ├─ ic_del2.svg
│     │     ├─ ic_enter.svg
│     │     ├─ ic_link.svg
│     │     ├─ ic_login.svg
│     │     ├─ ic_logout.svg
│     │     ├─ ic_off.svg
│     │     ├─ ic_on.svg
│     │     ├─ ic_pic.svg
│     │     ├─ ic_reply.svg
│     │     ├─ ic_report.svg
│     │     ├─ ic_search.svg
│     │     ├─ ic_side.svg
│     │     ├─ index.js
│     │     ├─ left.svg
│     │     ├─ log_out.svg
│     │     ├─ menu.svg
│     │     ├─ right.svg
│     │     └─ support.svg
│     ├─ baseStyles
│     │  └─ index.js
│     ├─ components
│     │  ├─ checkbox
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ comment
│     │  │  ├─ api
│     │  │  │  └─ api.js
│     │  │  ├─ Comment.js
│     │  │  ├─ styles.js
│     │  │  └─ WriteSection.js
│     │  ├─ footer
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ gnb
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ index.js
│     │  ├─ issueBoard
│     │  │  ├─ icon
│     │  │  │  └─ SearchIcon.js
│     │  │  ├─ issueboardEdit
│     │  │  │  ├─ IssueboardEdit.js
│     │  │  │  └─ styles.js
│     │  │  └─ issueList
│     │  │     ├─ index.jsx
│     │  │     └─ styles.js
│     │  ├─ loading
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ modal
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ noticeMinBoard
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ passwordInput
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ report
│     │  │  ├─ attachedFilesEach
│     │  │  │  ├─ attachedFilesEach.jsx
│     │  │  │  └─ styles.js
│     │  │  └─ detail
│     │  │     ├─ delBtn
│     │  │     │  ├─ index.jsx
│     │  │     │  └─ styles.js
│     │  │     ├─ fileList
│     │  │     │  ├─ index.jsx
│     │  │     │  └─ styles.js
│     │  │     ├─ saveBtn
│     │  │     │  ├─ index.jsx
│     │  │     │  └─ styles.js
│     │  │     └─ submissionBtn
│     │  │        ├─ index.jsx
│     │  │        └─ styles.js
│     │  ├─ reportListEach
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ sideBar
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ swiper
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ template
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ toast
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ topBanner
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ topBar
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  └─ validateInput
│     │     ├─ index.jsx
│     │     ├─ model.js
│     │     └─ styles.js
│     ├─ constants
│     │  ├─ contentConstant.js
│     │  ├─ fileAttachConstant.js
│     │  ├─ logicConstant.js
│     │  ├─ modalConstant.js
│     │  ├─ pathConstant.js
│     │  ├─ uiConstant.js
│     │  └─ urlConstant.js
│     ├─ dummyData
│     │  ├─ allianceDatas.js
│     │  ├─ inquiryDatas.js
│     │  ├─ issueDats.js
│     │  ├─ noticeDatas.js
│     │  ├─ pointHistoryDatas.js
│     │  ├─ privacyPolicyData.js
│     │  ├─ qnaDatas.js
│     │  ├─ reportGuide.js
│     │  ├─ termData.js
│     │  └─ userData.js
│     ├─ index.css
│     ├─ index.jsx
│     ├─ initCss.css
│     ├─ layouts
│     │  ├─ Layout.jsx
│     │  ├─ model.js
│     │  ├─ styles.js
│     │  └─ SubLayout.jsx
│     ├─ pages
│     │  ├─ issueDetail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ issueEdit
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ issueList
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ issueSearch
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ login
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ main
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ mychannelDetail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ myChannelReportList
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ newPw
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportDetail
│     │  │  ├─ index.jsx
│     │  │  └─ styles.js
│     │  ├─ reportGuide
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportList
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ reportWrite
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ searchPw
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ searchPwSendEmail
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ signup
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  ├─ template
│     │  │  ├─ index.jsx
│     │  │  ├─ model.js
│     │  │  └─ styles.js
│     │  └─ terms
│     │     ├─ index.jsx
│     │     ├─ model.js
│     │     └─ styles.js
│     ├─ router
│     │  └─ index.jsx
│     ├─ setupTests.js
│     ├─ store
│     │  ├─ configureStore.js
│     │  ├─ index.js
│     │  └─ reducers
│     │     ├─ layoutReducer.js
│     │     ├─ modalReducer.js
│     │     ├─ rootReducer.js
│     │     ├─ toastReducer.js
│     │     └─ userReducer.js
│     └─ utils
│        ├─ axios
│        │  └─ index.js
│        └─ report
│           └─ detail
│              └─ index.js
├─ package-lock.json
└─ README.md

```

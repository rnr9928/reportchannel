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


# mvc 패턴을 이용한 기능 분리

## mvc패턴이 나오게 된 계기

과거에 수많은 개발자들이 수많은 프로그램들을 짰는데

프로그램들을 짤수록 코드들이 복잡해지고 코드를 파악하기도 힘들고

나중에 기능을 수정할 때 대부분의 코드를 갈아 엎아야 하는 경우가 많다고 합니다

한마디로 유지보수가 매우 불편한 경우가 많이있었죠

그렇게 계속  코드를 짜다가  비슷한 것끼리 나누기 시작했고

이렇게 코드 구성을 하니 유지보수가 편하다라는  걸 느끼게 되었죠

코드를 짤 때마다 점점 패턴들의  규칙성이  보이기 시작한겁니다

그렇게 그 패턴들을 하나의 공식처럼 만들어서 나온게 바로이 MVC 패턴

요약하자면   **MVC 패턴은**

유지보수가 편해지는 코드 구성 방식 ' 이라고 보시면 됩니다.

MVC패턴 구조

![image](https://github.com/rnr9928/reportchannel/assets/97073355/d8574389-f398-4163-b22f-3d8d24ea1b11)


1. 먼저 사용자가 구글에 '코딩'이라고 검색

2. 그러면 Controller는 검색결과를 달라고  Model 한테 요청

→ Model은 검색결과를 찾고 다시 Controller에게 전달

3. Controller는 검색결과를 View에게 전달

4.View는 사용자에게 이쁘게 나눠서 보여준다

여기서 알아야 하는게 **M**odel  ,  **V**iew , **C**ontroller들의 역할 입니다

Model은 데이터

즉, 데이터와 관련된 일을 하는 곳 입니다

Controller는 View와Model의 중개자 역할( 이어주는 역할 )을 하고 있는 것을 알 수 있죠

View는 사용자한테 보여지는 부분을 담당합니다

그럼 이제

MVC 패턴을  지키면서 코딩 하는 방법을 알아봅시다.

**1. Model은 Controller와 View에 의존하지 않는다**

쉽게 말하면

모델 내부에 컨트롤러와 뷰에 관련된 코드가 있으면 안된다라는 것인데.

모델은 데이터가 관련된 부분이니

언제든 깔끔하고 정제된 데이터를 꺼낼 쓸수 있게 하기 위해서이다

**2. View는 Model에만 의존해야하고 Controller에는 의존하면 안된다.**

뷰 내부에는 모델의 코드만 있을 수 있고

컨트롤러에 코드가 있으면 안된다.

**3. View가 Model로 부터 데이터를 받을 때는**

**사용자마다 다르게 보여줘야하는 데이터에 대해서만 받아야한다**

사진으로 예시를 보자면

![image (1)](https://github.com/rnr9928/reportchannel/assets/97073355/a346fddc-ccef-48af-a5b7-df3b2069faec)


빨간색으로 되있는 부분은 사용자마다 다르게 보여줘야하는 부분이죠

이렇게 View는 사용자한테 보이는 UI와

Model로부터  받은 데이터가 합쳐져 만들어진 화면입니다

주문하기 글씨 , 배경색 등은 Model로부터 받아오면 안되고

View가 자체적으로 가지고 있어야하는 정보들이죠

💡  데이터를 받을 때 반드시 Controller에서 받아야 합니다!

**4. Controller는 Model과 View에 의존해도 된다**

컨트롤러는 모델과 뷰의 중개자역할(이어주는역할)을 하면서

전체적인 로직을 구성하기 때문입니다

Model은

데이터의 형식을 지정하고 , 저장하고 불러오는 작업들에 관한 코드들이

View는

Html , css 요소가

Controller는

Model 과 View를 연결해주는 부분이라고 생각하시면 됩니다

# 적용해보기

![1](https://github.com/rnr9928/reportchannel/assets/97073355/aa2e32f5-538a-49b6-81a9-9a2c8020d622)


mvc 패턴을 숙지하면서 ui와 기능들을  따로 분리하면서 개발했습니다

![1 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/e3c2a433-6b21-4f7d-9c0c-41bc17026742)

![1 (2)](https://github.com/rnr9928/reportchannel/assets/97073355/bad505fc-9d44-41a2-b25c-d6449cba854b)


page폴더에는 웹 페이지 안에 있는 기능들을 보여주는 ui 입니다

components 폴더는 기능들을 구현한 코드들이 들어있습니다

![제목 없음](https://github.com/rnr9928/reportchannel/assets/97073355/088a3c86-e142-4a79-99f4-060b65b48f9d)

![제목 없음 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/da39c7ed-59e6-404d-a13c-46b195d8f9b3)


기능들을 import 하고 적용시킨 모습

--------------------------------------------------------------------------------------------------------------

# comment  설명

![1](https://github.com/rnr9928/reportchannel/assets/97073355/1b91d078-cfce-49d0-8471-f856bccbda9c)


**각 파일의 기능**

## **Comment.jsx**

![1 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/24c241d4-43f3-4f28-ac14-874654a2707a)


                            수정 , 삭제 , 답글  기능이 담겨진 댓글 컴포넌트 입니다

## **Comment2.js**

![1 (2)](https://github.com/rnr9928/reportchannel/assets/97073355/ff3309c3-27e9-4e4e-ace2-0d54df30e79e)


수정 , 삭제, 답글 기능을 **활성화** 하는 기능들이 담겨져 있습니다

자신이 쓴  덧글만 수정 삭제가 가능합니다

(true 상태일때 활성화)

## **WriteSection.js**

![1 (3)](https://github.com/rnr9928/reportchannel/assets/97073355/304e1ff1-3a8c-4555-9b5e-0dfe60ea0833)


댓글을 작성하는 ui가 들어있습니다.

# Moment 사용

![1 (4)](https://github.com/rnr9928/reportchannel/assets/97073355/da62b7f2-1f9c-4c5a-87c5-96f77b4aa3bd)


moment 라이브러리를 이용하여 날짜와 시간표시를 구현했습니다

**`timeData`** 변수에는 **댓글 작성시간**을 가져옵니다

**`currentMoment`와 `dataMoment`** 사이의 날짜 차이를  계산하여 “day”를 구했습니다

**dayGap**이 10이상인 경우 **`timeData`** 값을 "**YYYY.MM.DD**" 형식으로 변환시켰습니다

10일 미만일 경우 “일전”으로 표시했습니다

# react-query 사용

![Untitled](https://github.com/rnr9928/reportchannel/assets/97073355/8701e0a0-d86c-4b68-9c1d-acbbdd1e3585)


- **기존의 비동기  로직 처리 (ex. redux ,  redux-saga)**
    - 성공, 실패  모두 일일히 선언
    - 서버  데이터가 fetch를 수행해야만 최신 데이터 상태
        - 여러 컴포넌트에서 최신 데이터를 받아올려면 그  만큼 fetch수행
- r**eact-query 사용**
    
    
![1 (5)](https://github.com/rnr9928/reportchannel/assets/97073355/a873fffd-fc29-487a-9537-477a872b2a6e)

    

• useQuery의 반환 값을 활용하여 성공, 실패 처리 가능 ( isFetching, isLoading, error, state 등 )

- useQuery 첫 번째 인자인 `QueryKey`에 따라서 캐싱 처리. 캐싱된 쿼리의 `QueryKey`와 동일한 요청을 하는 쿼리는 같은 것으로 인식하여 fetch하지 않고 캐싱된 쿼리 그대로 사용.
    - 여기서 `QueryKey`는 user
    - string, array, object 등 유니크한 값이면 된다.
    - array일 경우 순서가 서로 바뀌어도 unique
    - object는 순서가 바뀌면 같은 값으로 인식
- 두 번째 인자 fetcher는 프로미스를 반환하는 함수여야 한다.
- 세 번째 인자 options에는 캐시 만료 시점, refetch 시점, 초기값 등을 설정할 수 있으며 생략 가능하다.

---

![1 (6)](https://github.com/rnr9928/reportchannel/assets/97073355/8d6ec8d9-48e4-4dc7-84b5-b24f953e91a7)


리액트 쿼리 기능중 하나인 **useMutation()**을 사용

서버와의 데이터 동기화를 신경쓰지 않고 먼저 사용자에게 성공 시 UI를 보여준 후

요청의 결과가 오면 성공/실패 여부에 따라 ui 업데이트

• 예: 인스타그램의 좋아요 기능, 카카오톡이 일단 전송된 후 성공, 취소/재전송 창이 나중에 뜨는 것

## 문제

데이터가 캐싱되어 있어서 

로그아웃을해도 댓글이 작성되는 문제가 있었다 

## 해결

onSuccess 콜백으로 invalidateQueries를 사용해서 “myChannelDetailComments” 키값에  해당  데이터를 적용시키면  해당 데이터는 만료된 상태가 되어 refetching 된다

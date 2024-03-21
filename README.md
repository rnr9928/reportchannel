

## fork해온 레퍼지토리의 main브런치와 merge

    <img width="668" alt="pull6" src="https://user-images.githubusercontent.com/107897812/211038661-58c71630-b4f2-49ff-9c95-88b2f1da6d7b.png">

    <img width="665" alt="pull7" src="https://user-images.githubusercontent.com/107897812/211038667-c04b4990-f1f9-49c6-b64f-3a6cb5df51e4.png">

# mvc 패턴을 이용한 기능 분리

  **MVC 패턴**

유지보수가 편해지는 코드 구성 방식
-------------------------------------------------------------------------------------------------------------------------------------

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

![image (1)](https://github.com/rnr9928/reportchannel/assets/97073355/bdf9b480-930e-40fe-8bb4-222bca7ef4f5)


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

![1](https://github.com/rnr9928/reportchannel/assets/97073355/d316878d-e8a7-49fd-af83-3014fac61ed1)


mvc 패턴을 숙지하면서 ui와 기능들을  따로 분리하면서 개발했습니다

![1 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/c715bc79-ef4d-4ce2-a151-205f00a0c2dc)

![1 (2)](https://github.com/rnr9928/reportchannel/assets/97073355/89af2f2f-dd0e-4219-a93a-f866b2249ea6)


page폴더에는 웹 페이지 안에 있는 기능들을 보여주는 ui 입니다

components 폴더는 기능들을 구현한 코드들이 들어있습니다

![제목 없음](https://github.com/rnr9928/reportchannel/assets/97073355/2250ada9-9d19-4bff-859e-60dfef59c889)

![제목 없음 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/697b704f-9820-4bbe-8ce7-b87c225b7e75)


기능들을 import 하고 적용시킨 모습

------------------------------------------------------------------------------------------------------------------------------


# comment  설명
![1](https://github.com/rnr9928/reportchannel/assets/97073355/c8cdb0b2-2788-4dd7-9b80-34735b701c6e)



**각 파일의 기능**

## **Comment.jsx**

![1 (1)](https://github.com/rnr9928/reportchannel/assets/97073355/88c1cf1a-b7e7-428e-a65d-1802cfcd8607)


                  수정 , 삭제 , 답글  기능이 담겨진 댓글 컴포넌트 입니다

## **Comment2.js**

![1 (2)](https://github.com/rnr9928/reportchannel/assets/97073355/de0094e9-813c-4505-976d-64a72961d60f)


수정 , 삭제, 답글 기능을 **활성화** 하는 기능들이 담겨져 있습니다

자신이 쓴  덧글만 수정 삭제가 가능합니다

(true 상태일때 활성화)

## **WriteSection.js**

![1 (3)](https://github.com/rnr9928/reportchannel/assets/97073355/b9320380-612e-4ac7-a267-9431be31f1fd)


댓글을 작성하는 ui가 들어있습니다.

# Moment 사용

![1 (4)](https://github.com/rnr9928/reportchannel/assets/97073355/618556fa-45de-4e85-8850-4591a28adad1)


moment 라이브러리를 이용하여 날짜와 시간표시를 구현했습니다

**`timeData`** 변수에는 **댓글 작성시간**을 가져옵니다

**`currentMoment`와 `dataMoment`** 사이의 날짜 차이를  계산하여 “day”를 구했습니다

**dayGap**이 10이상인 경우 **`timeData`** 값을 "**YYYY.MM.DD**" 형식으로 변환시켰습니다

10일 미만일 경우 “일전”으로 표시했습니다

# react-query 사용

![Untitled](https://github.com/rnr9928/reportchannel/assets/97073355/1fbc2af5-dc3e-4206-a25f-fcb10b99932f)


- **기존의 비동기  로직 처리 (ex. redux ,  redux-saga)**
    - 성공, 실패  모두 일일히 선언
    - 서버  데이터가 fetch를 수행해야만 최신 데이터 상태
        - 여러 컴포넌트에서 최신 데이터를 받아올려면 그  만큼 fetch수행
- r**eact-query 사용**
    
    
![1 (5)](https://github.com/rnr9928/reportchannel/assets/97073355/bbf82ab1-d9b0-4562-9f8c-6e51956b21ef)

    

• useQuery의 반환 값을 활용하여 성공, 실패 처리 가능 ( isFetching, isLoading, error, state 등 )

- useQuery 첫 번째 인자인 `QueryKey`에 따라서 캐싱 처리. 캐싱된 쿼리의 `QueryKey`와 동일한 요청을 하는 쿼리는 같은 것으로 인식하여 fetch하지 않고 캐싱된 쿼리 그대로 사용.
    - 여기서 `QueryKey`는 user
    - string, array, object 등 유니크한 값이면 된다.
    - array일 경우 순서가 서로 바뀌어도 unique
    - object는 순서가 바뀌면 같은 값으로 인식
- 두 번째 인자 fetcher는 프로미스를 반환하는 함수여야 한다.
- 세 번째 인자 options에는 캐시 만료 시점, refetch 시점, 초기값 등을 설정할 수 있으며 생략 가능하다.

---

![1 (6)](https://github.com/rnr9928/reportchannel/assets/97073355/b6a07414-2b94-4486-aeec-2a7d3fefe732)



리액트 쿼리 기능중 하나인 **useMutation()**을 사용

서버와의 데이터 동기화를 신경쓰지 않고 먼저 사용자에게 성공 시 UI를 보여준 후

요청의 결과가 오면 성공/실패 여부에 따라 ui 업데이트

• 예: 인스타그램의 좋아요 기능, 카카오톡이 일단 전송된 후 성공, 취소/재전송 창이 나중에 뜨는 것

로그아웃을해도 댓글이 작성되는 문제가 있었다 

## 해결

onSuccess 콜백으로 invalidateQueries를 사용해서 “myChannelDetailComments” 키값에  해당  데이터를 적용시키면  해당 데이터는 만료된 상태가 되어 refetching 된다

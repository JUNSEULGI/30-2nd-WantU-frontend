## Want U
원츄는 원티드를 모티브로 구직/채용 사이트로, 이력서를 업로드하고 채용공고에 지원하기까지의 로직에 집중하여 프로젝트를 진행하였습니다. 원하는 채용 공고 조건 검색, 공고 상세 페이지, 이력서 업로드 및 다운로드, 카카오 소셜 로그인까지 하나의 플로우를 구현했습니다.
<br/>

### 개발 기간 및 인원
#### 개발 기간
- 2022.03.14 ~ 2022.03.25

#### 개발 인원
- FE
  * 박별 : 공통 컴포넌트 Nav/Footer, 카카오톡 소셜로그인 페이지, 공고 리스트 페이지
  * 전슬기 : 공고 상세 페이지, 마이페이지(지원현황&이력서 관리)
- BE
  * 박영서
  * 이예솔
<br/>

## Target site
### 사이트 소개
- [원티드](https://www.wanted.co.kr/wdlist/518?country=kr&job_sort=company.response_rate_order&years=-1&locations=all)
### 사이트 선정 이유
- 깔끔한 UI
- 다양한 카테고리 및 필터링 기능
- 파일 업로드 및 수정 기능
<br/>

## 📝 적용 기술 및 구현 기능

<img src = "https://github.com/wingna1/wantuPicbase/blob/main/wantuGIF.gif">


### 구현기능
* Nav & Footer
    - Nav : 호버 시 2단 드롭다운 메뉴가 나타나 카테고리 보여줌
    - Footer : 타겟 사이트 원티드의 footer와 유사하게 구현
* 소셜 로그인
    - 조건부렌더링을 이용하여 로그인 창 띄움
    - stopPropagation()을 이용하여 배경을 클릭했을 때만 창이 꺼지는 모달창 구현
    - 인가코드 발급
    - 카카오 API에서 받은 토큰을 백엔드로 전송
    - 백엔드에서 생성한 토큰을 다시 받아서 로그인된 사용자임을 확인 
* 공고 리스트 페이지
    - query parameter를 이용해 카테고리, 태그, 지역에 따른 filtering과 제목순, 마감일순, 등록일순에 따른 sorting 적용
    - 페이지 하단의 prev, next 버튼 클릭 시, 백엔드로부터 해당 페이지의 공고 리스트를 받아와 보여주는 pagination 구현
    - useNavigate() 훅을 이용하여 해당 id의 공고 상세페이지로 이동
* 공고 상세 페이지
    - path parameter로 상품 id를 백엔드에 전달하여 공고 상세페이지에 필요한 데이터를 받아와 그려냄
    - 로그인이 되어있을 때만 지원하기 가능
    - 이름, 이메일은 사용자의 정보를 받아와서 자동으로 입력하고, 전화번호와 제출할 이력서까지 입력해야 버튼 활성화
    - 이력서 파일을 추가로 업로드 가능
* 마이페이지
    - 백엔드로부터 데이터를 받아와 지원 상태별 지원 현황을 보여줌
    - 업로드된 이력서 파일을 보여주고, 추가로 업로드하거나 이름변경, 삭제,  가능
<br><br>

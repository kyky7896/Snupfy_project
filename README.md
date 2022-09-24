# Search for Netrient-Balanced Food for You : SNuBFY

Git-Hub: 

Link:

# 1. INTRO

### 🎄 팀 소개

- 팀명 :  SNubFy(Search for Nutrient-Balanced Food for you)
- 팀원 : 이경영(팀장), 김보람, 박선민, 정주영
- 역할
    - 추천시스템 설계(알고리즘 구현, 모델링) : 김보람, 박선민
    - Front-End: 이경영
    - Back-End: 정주영, 이경영

### 🎄 프로젝트 소개

- 주제 :  영양소 기반 재료 추천 및 레시피 제공 시스템
- 기간: 2022.08.08 ~ 2022.09.16 [6주간 진행]
- 세부 계획
    - 1주차(2022.08.08.(월) ~ 2022.08.14.(일))
        - 프로젝트 주제 선정
        - 기획안 작성 및 역할 분담
        - 프로젝트에 필요한 데이터 준비
    - 2주차(2022.08.15.(월) ~ 2022.08.21.(일))
        - 데이터 크롤링 작업 및 셋팅
        - 데이터 분석
        - 데이터 전처리 작업
    - 3주차(2022.08.22.(월) ~ 2022.08.28.(일))
        - Python 활용하여 기능별 알고리즘 구현
        - 추천시스템에 활용될 모델 학습 및 테스트
    - 4주차(2022.08.29.(월) ~ 2022.09.04.(일))
        - 모델 보완 작업
        - Flask 활용하여 관리자 기능 작업
        - 추천시스템에 활용될 모델 학습 및 테스트
    - 5주차(2022.09.05.(월) ~ 2022.09.11.(일))
        - Flask 활용하여 사용자 기능 작업
        - 웹 디자인 및 기능 점검
        - 추천시스템에 활용될 모델 학습 및 테스트
    - 6주차(2022.09.12.(월) ~ 2022.09.16.(금))
        - 프로젝트 마무리 및 최종 점검
        - PPT 작성 및 발표 준비

# 2. PROJECT

## ✅ 요구사항


### 🎄 웹 기능

- 관리자: 상품 추가, 수정, 삭제 가능
- 사용자 기능
    - 회원 가입, 회원 정보 수정, 회원 탈퇴, 로그인, 로그아웃
    - 상품 구매, 상품 검색, 결제

### 🎄 시스템

- 영양소 추천 시스템
    - 회원 장바구니에서 식품 영양소 분석 진행
    - 영양소 부족할 경우, 보충할 수 있는 식품 추천
    - 회원정보(생년월일)를 바탕으로 연령대 별 영양소 분석하여 정보 제공
- 레시피 추천 시스템
    - 회원이 재료를 담았을 경우, 그 재료로 만들 수 있는 레시피를 보여줌
- 상품 추천 시스템
    - 상품끼리의 유사도 분석을 통해 상품 추천(main, 상품 페이지에서 제공)

### 🎄 데이터 활용

- 회원 정보(Kaggle - InstaCart Market 데이터셋 활용)
- 영양소 분석(FoodData Central API 활용)
- 레시피 (Kaggle - [Food.com](http://Food.com) Recipes and Interactions 데이터셋 활용)

## ✅ Service

### 🎄 메인 추천 기능

- 기존 회원: 구매 이력을 토대로 선호 식품 혹은 취향이 비슷한 사람들의 구매 상품을 추천
- 신규 회원: best-seller 기반 상품 추천 예정

### 🎄 상품 내 추천 기능

- 다른 고객이 함께 본 상품 구현

### 🎄 상품 내 **레시피 추천 기능**

- ‘recipe.csv’ 데이터 활용하여 재료로 만들 수 있는 다양한 레시피 추천

### 🎄 장바구니 내 **영양소 분석 및 추천 기능**

- 장바구니에 넣은 식품과 일일 영양소 권장 섭취량 기준 비교 분석
- 식품 추천
    - 장바구니에 넣은 상품의 영양소를 바탕으로 부족한 경우 대체할 수 있는 상품 추천

## ✅ Stack

- 크롤링 작업, 알고리즘 구성: Python
- 데이터 전처리: Pandas, Numpy
- 사용 모델:  CF, Word2vec 등
- 성능 측정: MAP, NDGC 외
- 웹 구현: Flask, sqlalchemy, HTML, CSS, Mysql, JavaScript

## ✅ Flow Chart


![Bro-Kurly2x_(1)](https://user-images.githubusercontent.com/77670592/192084165-206775d4-ceee-472c-ad83-66a2366f9c5f.png)

![%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-09-12_%EC%98%A4%ED%9B%84_8 51 07](https://user-images.githubusercontent.com/77670592/192084159-b1b13d5d-6aaf-40e1-a638-b0f7e72ead34.png)

![Untitled](https://user-images.githubusercontent.com/77670592/192084378-cc43b94b-c36c-4ba2-b95d-b9c66cc02f2c.png)

### 🎄 상세 설명

- 계정은 관리자 계정과 유저 계정 2가지로 구분
- 웹 메인 화면에서는 사용자 성향을 토대로 추천 식품을 보여줌
- 유저가 원하는 상품 선택 시, 상품의 상세 정보 페이지로 연결
- 상품 상세 정보 페이지에서  해당 식품으로 만들 수 있는 레시피와 다른 유저가 함께 구매한 식품을 보여줌
- 레시피 사진 선택 시, 레시피에 필요한 재료 정보를 보여줌
- 장바구니 선택 시, 장바구니 상품의 영양소와 회원정보를 바탕으로 연령대, 성별에 맞는 영양소 비교 분석하여 식품 추천 진행
- 부족한 영양소가 있을 경우: 영양을 보충할 수 있는 식품 추천
부족한 영양소가 없을 경우: 이전 구매 이력과 유사한 식품 추천
- 장바구니 상품에 만족할 경우, 결제 버튼 클릭 및 카드로 결제 진행
장바구니 상품에 만족하지 않을 경우, 다시 상품 둘러보기 페이지로 이동

# 3. MEMBERS

### 🎄 팀원 소개

- **이경영**: 빅데이터 분석 자바 파이썬 웹 개발자 양성 과정 수료
- **김보람:** 사회보장유레카 2022: 국민행복 서비스 발굴 창업 경진대회 공모전 우수상,
             디지털 헬스케어 MEDICAL HACK 2022 본선 진출
- **박선민:** 취향식탁(맞춤형 맛집 추천 어플) 개발
- **정주영:**  사회보장유레카 2022: 국민행복 서비스 발굴 창업 경진대회 공모전 우수상,
              취향식탁(맞춤형 맛집 추천 어플) 개발

**※ 공통**: AI_BootCamp PLAYDATA 인공지능 과정 교육 수강(2022.03.14. ~ 2022. 09. 16.)

사용 및 경험 언어: Python, MySQL, HTML, CSS, JAVA, Spring, JavaScript, Flask

### 🎄 주차별 세부 역할(확인/논의 필요)

- 1주차(팀 전체): 프로젝트 주제 선정, 기획안 작성, 데이터 준비
- 2주차
    - 데이터 전처리: 김보람, 박선민
    - Web Frame 구성 및 디자인 논의, 메인 및 회원가입 로그인 프레임 완료: 이경영
    - Back_end - Flask 공부: 정주영
    - 성별, 연령대 별 필요한 영양소 계산 알고리즘 구현: 박선민
    - 영양소 재료 추천 알고리즘 구현: 박선민
    - 추천 시스템에 활용될 모델 탐색: 김보람
    - Web_HTML, CSS 공부 : 이경영
- 3주차
    - 레시피 DataFrame 전처리 및 레시피 추천 시스템 구현 : 박선민
    - 상품 데이터 전처리: 김보람
    - Back_end_사용자 기능 구현(회원 가입, 로그인, 로그아웃) : 정주영
    - Web_주문목록, 상품등록, 상품리스트, 상품디테일 구현 : 이경영
    - Web_레시피 페이지 구성: 이경영
- 4주차
    - 상품, 레시피, 재료 DB 작성 및 상품 정보 크롤링 : 박선민
    - 상품 유사도 측정 및 알고리즘 구현, 모델 생성: 김보람
    - Front_end와 Back_end 코드 통합 : 정주영, 이경영
    - Back_end Blueprint 방식으로 리팩토링 : 정주영, 이경영
    - Web_상품디테일 추가수정분, 상품수정, 주문 디테일, 장바구니 페이지 구성 : 이경영
- 5주차
    - 추천 시스템 모델 성능 개선 및 테스트 : 김보람, 박선민
    - Back_end_ER diagram 수정 및 mysql db연동 : 정주영, 이경영
    - Back_end_상품 추천, 레시피 추천 기능: 이경영
    - Back_end_상품 CRUD : 이경영
- 6주차(팀 전체): 기능 최종 점검, PPT 작성 및 발표 준비

### 🎃 필요한 페이지(보여져야 할 부분)

- 메인 - 회원가입, 로그인, 로그아웃, 마이페이지, 상품 추천
- 회원 - 필수 입력(이름, 주민등록번호 6자리 + 성별 체크 1자리 , 휴대폰 번호, 집 주소, 아이디, 비밀번호, 비밀번호 재확인, 이메일 주소, 관리자 유무)
- 내 정보 보기 - 회원 정보, 주문 목록
- 주문 목록 - 주문 번호, 상품, 가격, 수량, 결제금액, 배송지 주소
- 상품 - 상품 소개, 상품 이미지, 영양 성분, 구매 수량, 단가, 장바구니 담기, 레시피 추천, 상품 추천
- 레시피 - 레시피 이미지, 설명, 상품(재료로 쓰일 상품)
- 장바구니 - 배송지 주소 수정, 상품 목록, 수정, 삭제, 수량, 금액, 최종 결제 금액, 영양소 분석, 영양소 추천 상품, 결제 수단(카드) 정보 기입, 주문하기
- 결제- 카드 비밀번호 입력(임의로 입력) , 결제 버튼, 결제 취소 버튼

---

---

[회의록 ](https://iris-unicorn-3d1.notion.site/1c66ff825c614e6c869a1a278a145589)

[트러블슈팅 관련](https://iris-unicorn-3d1.notion.site/09599bf1304142f6b9fd7ba8b13c26b1)

[Dataset](https://iris-unicorn-3d1.notion.site/Dataset-a71f4dd5964e4289a3795a2c2693c04f)

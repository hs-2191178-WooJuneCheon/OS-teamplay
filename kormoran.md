 # Komoran 조사
 1991317 양윤석

 ## 1. KORMORAN 
kormoran은 java로 개발된 한국어 형태소 분석기이다.

## 2. 특징

### Pure Java

100% Java로만 개발되었기 때문에 자바가 설치된 환경이라면 어디서든지 사용 가능합니다.
### 외부 라이브러리 독립적

자체 제작한 Library들만을 사용하여 외부 Library와의 의존성 문제가 없습니다.
 ### 경량화

자소 단위 처리, TRIE 사전 등으로 약 50MB 메모리 상에서도 동작 가능합니다.
### Easy to Use

Library 적용 후 소스 코드 내 1줄만 추가하여 형태소 분석기를 사용할 수 있습니다.
### 사전 관리 용이

일반 텍스트 파일의 형태로 구성되어 가독성이 높으며 바로 편집이 가능합니다.
### 새로운 분석 결과

타 형태소 분석기와 달리 공백이 포함된 형태소 단위로 분석이 가능합니다.

## 3. 라이선스
Apache 2.0 License

## 4. '맥주 뭐 먹주'에서의 활용

- **맥주 리뷰데이터 토큰화**

    `scrapy`를 이용해 Beeradvocate 에서 수집해온 '맥주정보데이터'와 '맥주리뷰데이터' 중 '맥주리뷰데이터'는 유사 맥주와 사용자가 선호하는 맛의 맥주를 추천하는데 이용한다. 
    
     '맥주리뷰데이터'에는 맥주 맛에 대한 다양한 표현들이 담겨있다는 사실을 알 수 있었다. 따라서 이 맥주 맛을 표현하는 단어를 빈도수 기반으로 분석하면 특정 맥주의 맛 데이터를 얻을 수 있다고 생각했다. 따라서 단어 분석을 위해 리뷰를 토큰화할 필요가 있었고, 리뷰 토큰화에 `Kormoran`을 이용하기로 했다. `Kormoran`을 통해 생성된 토큰을 내부적으로 정제하여 맛을 표현하는 토큰들을 얻어내고, 각 맥주별 토큰의 빈도수를 종합하여 가중치 데이터를 만든다. 

    각 맥주의 가중치 데이터는 코사인 유사도 알고리즘을 이용하여 분석하고, 이 부분은 코드로 직접 구현한다. 앞의 과정을 통해 가중치 데이터가 유사한 맥주들을 추려 낼 수 있고, 이 것은 검색한 맥주와 비슷한 맥주, 사용자가 선호하는 맛과 유사한 맛의 맥주를 추천하는데 이용한다. 
    
    맥주 리뷰에서 정제한 맛 표현 단어들은 카테고리화 하여 '맥주뭐먹주' 앱 내에서 사용자가 리뷰를 남길 때, 선호하는 맛을 설정할 때 선택하게 한다. 카테고리화 된 맛 표현들로 후기를 남기면 다른 사용자들이 일관성있는 후기를 편리하게 볼 수 있을 뿐만 아니라, 우리가 맥주 가중치 데이터를 갱신하는데 활용 할 수 있다.  







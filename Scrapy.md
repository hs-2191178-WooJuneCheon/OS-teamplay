 # Scarpy 조사
 1991317 양윤석
 
 ## 1. Scrapy
`Scrapy`는 Python으로 작성된 오픈소스 웹 크롤링 프레임워크이다

## 2. 라이선스
 BSD License

## 4. '맥주 뭐 먹주'에서의 활용

'맥주 뭐 먹주' 서비스의 기반이 되는 모든 데이터는 `scrapy`를 이용해 웹 사이트에서 수집해 온다. 맥주 정보 데이터는 맥주 정보 사이트인 'BeerAdvocte'에서  가져오는데, 가져오는 데이터는 '맥주 리스트','각 맥주의 정보','평점','리뷰'이다. 데이터들은 `postgreSQL`을 통해 데이터 베이스에 저장한다. 저장 형식은 다른 오픈소스 소프트웨어와의 연동을 위해 `JSON`으로 한다. 저장된 '각 맥주의 정보'는 사용자에게 제공하고, '리뷰'는 토큰화를 통해 맥주 맛 데이터를 형성하는데 사용한다. 

사용자에게 맥주 관련 정보를 제공하는 서비스를 만들기 위해 네이버 게시글을 이용한다. `scrapy`를 이용하여 네이버 `게시글과`, 게시글의 `해시태그`, `URL`을 가져온다. 어떤 게시글을 가져올지에 대한 기준은 '맥주리스트'의 맥주 이름 키워드와 "맥주" 단어로 한다. 해시태그는 사용자의 검색에 대한 관련 게시물 추천에서 이용되는데 `ElasticSearch`에서 내부적인 처리를 통해 사용자에게 적절한 게시물을 제공한다.         
  






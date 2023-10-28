![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=250&section=header&text=Sentyle&fontSize=80&animation=fadeIn&fontAlignY=35&descSize=15&desc='Sent'iment%20and%20S'tyle'&descAlignY=50&descAlign=43&fontColor=FFFFFF)


# 👟👜 Sentyle 👚👖
KOELECTRA를 활용하여 패션 쇼핑몰 리뷰 데이터 감성 분석 및 긍부정 예측

## 1. 개요

   * ### 문제정의

     현대 사회에서 패션은 단순히 옷을 입는 것을 넘어서 개인의 정체성과 스타일을 표현하는 중요한 수단으로 자리잡고 있다.
     사람들은 더 이상 옷을 단순히 실용적인 도구로만 보지 않고, 자신의 취향, 가치관, 문화적 배경을 반영하는 패션 아이템을 찾고 소비하는 경향이 높아졌다.

     <img width="450" alt="chart1" src="https://github.com/wnaely/Sentyle/assets/130523834/7cf8ea06-d124-4aa0-8a4a-5a143d41ad5c">
     <img width="500" alt="chart2" src="https://github.com/wnaely/Sentyle/assets/130523834/cd7e82c0-1cc5-484c-b180-bf699d30f708"> <br>
     (출처: DAILY POP 경제 기사 <sup><a href="https://www.dailypop.kr/news/articleView.html?idxno=65004">[01]</a></sup>) /
     (출처: WISEAPP 인사이트 <sup><a href="https://www.wiseapp.co.kr/insight/detail/408">[02]</a></sup>)

   
     작년 겨울인 22년도 11월에 한 모바일 홈쇼핑 플랫폼을 이용하는 사용자들이 가장 많이 시청한 상품군은 '패션/잡화'였다. 해당 트렌드 리포트에 따르면, '패션/잡화' 상품군은 전체 시청수의 66.6%를 차지하는 것으로 조사되었다.
     이 결과에서 패션에 대한 사람들의 관심과 수요가 많다는 것을 알 수 있고, 모바일 홈쇼핑 플랫폼을 통한 패션 제품의 수요가 높아지고 있다는 것은 온라인 패션 시장이 계속 성장하고 있음을 나타낸다. 


     이러한 패션에 대한 관심은 전자상거래 업계에도 큰 영향을 미쳤으며, 온라인 패션 플랫폼들은 소비자들이 쉽고 편리하게 원하는 제품을 찾고 구매할 수 있도록 다양한 기능과 서비스를 제공하고 있다.

     온라인 패션 쇼핑몰은 소비자들에게 집에서 편안하게 쇼핑을 즐길 수 있는 기회를 제공하며, 바쁜 현대인들에게 시간을 절약할 수 있도록 도와준다.
     또한 다양한 제품과 스타일을 비교하고 선택할 수 있어 소비자의 선택 폭을 넓혀주었고, 온라인 리뷰와 SNS를 통해 다른 소비자들의 의견을 듣고 제품을 선택할 수 있는 기회를 제공하여 소비자의 신뢰를 얻고 있다.

<hr>


## 2. 데이터

   * ### 데이터 및 모델 개요
     데이터는 AI Hub에서 제공하는 [쇼핑몰 리뷰 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=71603)를 활용하여, 총 4만5천 건의 데이터에 대해서 사전 학습 언어 모델의 재학습(fine-tuning)을 수행한다.

     | 입력 | 모델 | 출력 |
     |----------|---|---|
     | 쇼핑몰 리뷰 문장 | KOELECTRA small <sup>[[01]](https://huggingface.co/monologg/koelectra-small-discriminator)</sup> | 부정(0), 긍정(1) |
     

     쇼핑몰 리뷰 문장은 전처리를 통해서 가공한다.
     대표적인 전처리로는 결측치와 중복값을 제거하고, 띄어쓰기로 구분이 되지 않는 리뷰 역시 제거한다.
     
      
   * ### 원본 데이터 소개

     #### [ 데이터 ]
       
     |INDEX|도메인|카테고리|상품명|상품평|데이터구분|
     |-|-|-|-|-|-|
     |6|패션|여성의류|OO 플** 베스트 풀코디 3종|여름에 편하게  막입기 조아요 특히 쪼끼가 젤 이뻐요|쇼핑몰|
     |7|패션|여성의류|OO 플** 베스트 풀코디 3종|가격이 착하고 디자인이 예쁩니다|쇼핑몰|
     |9|패션|여성의류|OO 플** 베스트 풀코디 3종|편하고 디자인이 예뻐요 가격도 좋아요 시원해요 빨리 마르고 이것만 입게되요|쇼핑몰|
     |...|...|...|...|...|...|
     |215103|패션|잡화|OO 아** 핸드백 3종|토트백 사이즈크고 좋아요. 끈 가죽재질 아니라 아쉽네요. 스퀘어백 사이즈 좋은작아요...|쇼핑몰|
     |215108|패션|잡화|OO 아** 핸드백 3종|검정색구매후 브라운색상 재주문했어요. 지퍼부분이 좀 불편하네요...|쇼핑몰|

   * ### 탐색적 데이터 분석

   * ### 데이터 전처리
     - 입력 데이터의 전처리 과정
     - 학습에 활용할 데이터의 양
     - 학습과 검증 데이터셋 분리
     - 학습 데이터의 구성
       
<hr>


## 3. 재학습 결과
   * ### 개발 환경
     - pycharm, python, torch, pandas, ...
     -
   * ### 3.2 KOELECTRA fine-tuning
   * ### 3.3 학습 결과 그래프

<hr>
     

## 4. 배운점

<hr>
       
       
   ## References
   [01] https://www.dailypop.kr/news/articleView.html?idxno=65004 <br>
   [02] https://www.wiseapp.co.kr/insight/detail/408
   
   [01] https://huggingface.co/monologg/koelectra-small-discriminator <br>




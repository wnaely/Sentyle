![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=250&section=header&text=Sentyle&fontSize=80&animation=fadeIn&fontAlignY=35&descSize=15&desc='Sent'iment%20and%20S'tyle'&descAlignY=50&descAlign=43&fontColor=FFFFFF)


# 👟👜 Sentyle 👚👖
KOELECTRA를 활용하여 패션 쇼핑몰 리뷰 데이터 감성 분석 및 긍부정 예측

## 1. 개요

   * ### 문제정의

     현대 사회에서 패션은 단순히 옷을 입는 것을 넘어서 개인의 정체성과 스타일을 표현하는 중요한 수단으로 자리잡고 있다.
     사람들은 더 이상 옷을 단순히 실용적인 도구로만 보지 않고, 자신의 취향, 가치관, 문화적 배경을 반영하는 패션 아이템을 찾고 소비하는 경향이 높아졌다.

     <img width="450" alt="chart1" src="https://github.com/wnaely/Sentyle/assets/130523834/7cf8ea06-d124-4aa0-8a4a-5a143d41ad5c">
     <img width="500" alt="chart2" src="https://github.com/wnaely/Sentyle/assets/130523834/cd7e82c0-1cc5-484c-b180-bf699d30f708"> <br>
     (출처: <a href="https://www.dailypop.kr/news/articleView.html?idxno=65004">DAILY POP 경제 기사</a>) /
     (출처: <a href="https://www.wiseapp.co.kr/insight/detail/408">WISEAPP 인사이트</a>)

   
     작년 겨울인 22년도 11월에 한 모바일 홈쇼핑 플랫폼을 이용하는 사용자들이 가장 많이 시청한 상품군은 '패션/잡화'였다. 해당 트렌드 리포트에 따르면, '패션/잡화' 상품군은 전체 시청수의 66.6%를 차지하는 것으로 조사되었다<sup><a href="https://www.dailypop.kr/news/articleView.html?idxno=65004">[01]</a></sup>. 또한 통계청의 온라인쇼핑 동향조사 결과, 2017년 31조 수준이었던 온라인 쇼핑몰의 연간 거래액은 2022년 77조로 5년 사이 147% 성장했다<sup><a href="https://www.wiseapp.co.kr/insight/detail/408">[02]</a></sup>. <br>
     이러한 결과를 통해 패션에 대한 사람들의 관심과 수요가 높다는 것을 알 수 있고, 모바일 홈쇼핑 플랫폼을 통한 패션 제품의 수요가 많아지고 있다는 것은 온라인 패션 시장이 계속 성장하고 있음을 나타낸다.
     <hr>

     온라인 패션 시장은 소비자들에게 편리한 쇼핑 경험을 제공한다. 가정이나 사무실에서 휴대폰이나 컴퓨터를 통해 언제든지 쇼핑을 할 수 있으며, 복잡한 절차 없이 간편하게 제품을 선택하고 구매할 수 있다.
     또한, 소비자들은 온라인 쇼핑을 통해 국내외 다양한 브랜드와 디자이너 제품에 접근할 수 있으며, 다양한 스타일과 가격대의 제품을 비교하며 원하는 제품을 찾을 수 있다. 추가로 신제품 출시나 세일 이벤트 등 다양한 할인 혜택도 받을 수 있다.

     하지만 온라인 쇼핑 특성상 제품의 실제 색상이나 품질을 직접 확인할 수 없다는 점을 고려해야 한다. 화면의 해상도나 색상 보정 등으로 인해 제품의 실제 색상이 다를 수 있으며 품질에 대한 확신을 얻기 어려울 수 있다.



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




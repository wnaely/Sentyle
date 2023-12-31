![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=250&section=header&text=Sentyle&fontSize=80&animation=fadeIn&fontAlignY=35&descSize=15&desc='Sent'iment%20and%20S'tyle'&descAlignY=50&descAlign=43&fontColor=FFFFFF)


# 👟👜 Sentyle 👚👖
KoELECTRA를 활용하여 패션 쇼핑몰 리뷰 데이터 감성 분석 및 긍부정 예측

## 1. 개요

   * ### 문제정의

     현대 사회에서 패션은 단순히 옷을 입는 것을 넘어서 개인의 정체성과 스타일을 표현하는 중요한 수단으로 자리잡고 있다.
     사람들은 더 이상 옷을 단순히 실용적인 도구로만 보지 않고, 자신의 취향, 가치관, 문화적 배경을 반영하는 패션 아이템을 찾고 소비하는 경향이 높아졌다.

     <h5><p align="center" width="100%">
     <img width="44%" src="https://github.com/wnaely/Sentyle/assets/130523834/7cf8ea06-d124-4aa0-8a4a-5a143d41ad5c">
     <img width="50%" src="https://github.com/wnaely/Sentyle/assets/130523834/cd7e82c0-1cc5-484c-b180-bf699d30f708"> <br>
     ( 출처: <a href="https://www.dailypop.kr/news/articleView.html?idxno=65004">DAILY POP 경제 기사</a> ) /
     ( 출처: <a href="https://www.wiseapp.co.kr/insight/detail/408">WISEAPP 인사이트</a> )</h5>
     </p>
     
     작년 겨울인 22년 11월에 한 모바일 홈쇼핑 플랫폼을 이용하는 사용자들이 가장 많이 시청한 상품군은 '패션/잡화'였다. 해당 트렌드 리포트에 따르면, '패션/잡화' 상품군은 전체 시청수의 66.6%를 차지하는 것으로 조사되었다<sup><a href="https://www.dailypop.kr/news/articleView.html?idxno=65004">[01]</a></sup>. 또한 통계청의 온라인쇼핑 동향조사 결과, 2017년 31조 수준이었던 온라인 쇼핑몰의 연간 거래액은 2022년 77조로 5년 사이 147% 성장했다<sup><a href="https://www.wiseapp.co.kr/insight/detail/408">[02]</a></sup>.
     
     위와 같은 결과를 통해 패션에 대한 사람들의 관심과 수요가 높다는 것을 알 수 있고, 모바일 홈쇼핑 플랫폼을 통한 패션 제품의 수요가 많아지고 있다는 것은 온라인 패션 시장이 계속 성장하고 있음을 나타낸다.

     온라인 패션 시장은 소비자들에게 편리한 쇼핑 경험을 제공한다. 가정이나 사무실에서 휴대폰이나 컴퓨터를 통해 언제든지 쇼핑을 할 수 있으며, 복잡한 절차 없이 간편하게 제품을 선택하고 구매할 수 있다.
     또한, 소비자들은 온라인 쇼핑을 통해 국내외 다양한 브랜드와 디자이너 제품에 접근할 수 있으며, 다양한 스타일과 가격대의 제품을 비교하며 원하는 제품을 찾을 수 있다. 추가로 신제품 출시나 세일 이벤트 등 다양한 할인 혜택도 받을 수 있다.

     <hr>

     <h5><p align="center" width="100%">
     <img width="49%" src="https://github.com/wnaely/Sentyle/assets/130523834/0e41e2e3-130d-4881-a8c7-25a0a0a543f9">
     <img width="49%" src="https://github.com/wnaely/Sentyle/assets/130523834/6d920de4-cddd-498c-9060-cf68036016b9"> <br>
     ( 출처: <a href="https://yozm.wishket.com/magazine/detail/1240/">위시켓 요즘IT</a> ) </p></h5>
     
     리뷰는 온라인 상에서 제공되는 정보 중 하나로, 소비자들이 실제로 사용하고 평가하는 내용이다. 이는 온라인으로만 판매되는 상황에서 소비자들이 제품에 대한 정보를 얻는 유일한 수단 중 하나이며, 해당 제품이 화면과 실물에서 색상이 같은지, 품질에 만족하는지 등을 확인할 수 있다.
     이런 정보를 바탕으로 소비자들은 구매 결정을 내릴 때 보다 현명하게 선택할 수 있다.

     온라인 패션 쇼핑몰은 리뷰 인센티브 지급이 가장 활발하다. 무신사 스토어, 지그재그, 에이블리 등은 리뷰를 작성한 구매자에게 현금처럼 사용할 수 있는 포인트를 지급하며, 이렇게 제품마다 작성된 리뷰의 여부에 따라 실제 구매로 이어지는 경우도 많았다. 리뷰가 있는 상품의 구매전환율은 리뷰가 없는 상품 대비 약 2.4배 높았고, 장바구니에 담기는 수치도 2.2배 높게 나타나는 등 리뷰가 구매에 큰 영향을 끼치는 것으로 조사됐다<sup><a href="https://www.m-i.kr/news/articleView.html?idxno=830313">[03]</a></sup>. <br>
     쇼핑 업계에서는 리뷰의 신뢰도와 편리성을 높이기 위해 ‘리뷰 검수 제도’와 ‘리뷰 정렬 기능’을 도입하는 등 리뷰 시스템에 큰 관심을 두고 있다.
     
     이러한 점들을 보았을 때 쇼핑몰에서의 리뷰는 종합적인 면에서 매우 중요한 것을 알 수 있다.
     따라서 이번 프로젝트에서는 패션 쇼핑몰 리뷰 데이터를 수집하고 분석하여 플랫폼의 장단점과 개선점을 파악하는 것을 목표로 하며, 이를 위해 AI Hub에서 제공하는 '쇼핑몰 리뷰 데이터'를 이용하여 리뷰의 긍정 혹은 부정을 예측하는 인공지능 모델을 개발하려고 한다.
     <hr>

   * ### 데이터 및 모델 개요
     데이터는 AI Hub에서 제공하는 [쇼핑몰 리뷰 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=71603)를 활용하여, 총 4만5천 건의 데이터에 대해서 사전 학습 언어 모델의 재학습(fine-tuning)을 수행한다.
     
     데이터는 2022년 쇼핑몰과 SNS 한글 리뷰 데이터로 구성되어 있고 패션, 화장품, 가전, IT기기, 생활 분야로 나눠져 있다.
     리뷰와 라벨링 데이터는 텍스트와 JSON 형태로 저장되어 있으며, 이중에서 패션 분야의 쇼핑몰 리뷰 데이터를 사용하여 프로젝트를 진행했다.

     | 입력 | 모델 | 출력 |
     |:------:|:------:|:------:|
     | 쇼핑몰 리뷰 문장 | KoELECTRA-Small-v3 <sup>[[04]](https://huggingface.co/monologg/koelectra-small-discriminator)</sup> | 부정(0), 긍정(1) |

     이번 프로젝트에서는 Hugging Face에 등록된 KoELECTRA-Small-v3 Discriminator의 토큰나이저 및 PreTrained 모델을 사용했다.
     
     KoELECTRA에서 "Ko"는 한국어를 나타내며, ELECTRA 모델을 한국어 자연어 처리 작업에 맞게 사전 학습한 모델을 가리킨다. 
     ELECTRA는 Google에서 발표한 모델로, BERT와 같이 트랜스포머(Transformers) 아키텍처를 기반으로 한다. <br>
     KoELECTRA는 대규모 한국어 텍스트 데이터 말뭉치를 훈련하여 텍스트 분류, 명명 개체 인식, 감성 분석 등 다양한 한국어 자연어 처리 작업에서 최고 수준의 성능을 달성했다<sup>[[05]](https://aws.amazon.com/ko/blogs/tech/kurly-sagemaker-product-review-classification-model/)</sup>.
     KoELECTRA는 오픈소스 프로젝트로 연구 커뮤니티에 공개되어 한국어 자연어 처리 작업의 정확도와 효율성을 높이기 위해 다양한 응용 분야에서 활용되고 있다.


     
<hr>


## 2. 데이터
      
   * ### 탐색적 데이터 분석

     #### [ 데이터 ]
       
     |INDEX|도메인|카테고리|상품명|상품평|데이터구분|
     |:-:|:-:|:-:|:-:|:-:|:-:|
     |6|패션|여성의류|OO 플** 베스트 풀코디 3종|여름에 편하게  막입기 조아요 특히 쪼끼가 젤 이뻐요|쇼핑몰|
     |7|패션|여성의류|OO 플** 베스트 풀코디 3종|가격이 착하고 디자인이 예쁩니다|쇼핑몰|
     |9|패션|여성의류|OO 플** 베스트 풀코디 3종|편하고 디자인이 예뻐요 가격도 좋아요 시원해요 빨리 마르고 이것만 입게되요|쇼핑몰|
     |...|...|...|...|...|...|
     |215103|패션|잡화|OO 아** 핸드백 3종|토트백 사이즈크고 좋아요. 끈 가죽재질 아니라 아쉽네요. 스퀘어백 사이즈 좋은작아요...|쇼핑몰|
     |215108|패션|잡화|OO 아** 핸드백 3종|검정색구매후 브라운색상 재주문했어요. 지퍼부분이 좀 불편하네요...|쇼핑몰|


     #### [ 라벨링 데이터 일부 ]

     |Index|RawText|MainCategory|productName|ReviewScore|Syllable|Word|RDate|GeneralPolarity|
      |:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
      |구분ID|리뷰데이터 소스 정보|해당상품이 속해있는 카테고리|리뷰 대상의 상품명|상품평 스코어|상품평 음절수|상품평 어절수|데이터 생성일자|상품평 전체 감정 극성| 

      "Index": "15", <br>
    "RawText": "편하고  디자인이 예뻐요  가격도  좋아요   시원해요  빨리 마르고  이것만  입게되요", <br>
    "MainCategory": "여성의류", <br>
    "ProductName": "OO 플** 베스트 풀코디 3종", <br>
    "ReviewScore": "100", <br>
    "Syllable": "49", <br>
    "Word": "10", <br>
    "RDate": "20210804", <br>
    "GeneralPolarity": "1" <br>

     라벨링된 데이터에서 상품평 리뷰 긍부정 라벨인 "GeneralPolarity" 데이터를 기존 원본 데이터에 추가하였다. 1이 긍정, 0이 중립, -1은 부정으로 라벨링 되어 있으며, 라벨링이 되어있지 않은 애매한 리뷰는 no general polarity로 분류하였다.

     <p align="center" width="100%">
     <img width="49%" src="https://github.com/wnaely/Sentyle/assets/130523834/9a663e1f-26d3-4bb5-ba7c-5dcec1af9144">
     <img width="49%" src="https://github.com/wnaely/Sentyle/assets/130523834/d937e4a6-4f03-442d-a2ad-3c4c00af737d"></p>

     데이터를 시각화 해 보았을 때 패션 카테고리 별 리뷰의 분포는 여성의류 관련 리뷰가 19,478개로 가장 많고 잡화 관련 리뷰가 3,930개로 가장 적은 것을 알 수 있다. 남성의류 관련 리뷰는 10,002개로 여성의류 보다 9,000개 이상 적었고, 패션 슈즈 관련 리뷰는 1,590개로 4개의 카테고리 중에서 두번째로 높은 비중을 차지했다.

     데이터의 긍부정 라벨링 분포에서는 긍정적인 리뷰가 26,457개로 가장 많았으며, 부정적인 리뷰와 중립인 리뷰는 각각 9,267개, 8,687개로 긍정적인 리뷰에 비해 확연히 적은 것을 확인할 수 있다. 라벨링 되지 않은 데이터인 'no general polarity'는 589개로 나타났다.
     <hr>
     
     
   * ### 데이터 전처리

     분석 결과와 모델 학습의 효과를 향상시키기 위해 전처리 작업을 수행하였다.
     
     애매하거나 중립인 리뷰는 감성 분석의 정확도를 낮출 수 있기 때문에 제외하고, 결측치와 중복값도 제거하였다.
     또한 제한된 텍스트로 인해 의미 있는 정보가 부족한 15자 미만의 짧은 리뷰 데이터도 삭제하였다.<br>
     리뷰 중에 줄바꿈이 있는 경우 줄바꿈(\n)을 공백으로 대체하였고, label이 -1인 부정 리뷰를 label 0으로 변경하여 최종 데이터셋을 준비했다.

     45,000건이었던 원본 데이터에서 전처리를 마친 후 <b>최종 데이터셋은 35,651건</b>이 되었다.

     ```python
     # 중복값 제거
     data.drop_duplicates(subset=['review'], inplace=True)
     
     # 결측치 제거
     data = data.dropna(how='any')

     # 리뷰가 15자 이상 500자 이하인 행들만 선택하여 데이터셋 구성
     data['length'] = data['review'].str.len()
     data = data[(data['length'] >= 15) & (data['length'] <= 500)]

     # '줄바꿈(\n)'을 공백으로 대체
     data['review'] = data['review'].str.replace("[\n]"," ")

     # label이 -1인 부정 리뷰를 0으로 label 변경
     for j in range(len(data['label'])):
     if data['label'][j] == -1: data['label'][j]=0
     ```

     |전처리 내용|예시|전처리 후 데이터의 개수|결과|
     |:-:|:-:|:-:|:-:|
     |중복, 결측치 제거|중복값: 4개, 결측치: 4개|44,992|중복, 결측치 삭제|
     |애매한 리뷰 제거|뒷굽은 쿠션이 있지만 앞쪽은 얇아서 쿠션감은 별로네요. 가벼워서 착용감은 좋아요|35,716|애매한 리뷰 삭제|
     |15자 미만 리뷰 제거|얇고 통이 커요|35,651|15자 미만 리뷰 삭제|
     |줄바꿈(\n)을 공백으로 대체|목둘레가 좀 좁아 조심히 다뤄야합니다<br>색상 맘에들고 특히 밍크 부분이 맘에 들고<br>따뜻합니다|35,651<br>(위와 동일)|목둘레가 좀 좁아 조심히 다뤄야합니다 색상 맘에들고 특히 밍크 부분이 맘에 들고 따뜻합니다|
     |label 변경|긍정: 1, 부정: -1|35,651<br>(위와 동일)|긍정: 1, 부정: 0|

     <hr>
      
     <p align="center" width="100%">
     <img width="53%" src="https://github.com/wnaely/Sentyle/assets/130523834/499d4972-0944-4beb-af18-16985e19e9cb">
     <img width="46%" src="https://github.com/wnaely/Sentyle/assets/130523834/1aaec4d5-9452-41a1-aaff-3df529ca0cde"></p>


     전처리 후 데이터를 살펴보면 리뷰 데이터의 문장 길이는 100자 이하에 가장 많이 몰려있고, 200자 이상인 리뷰는 거의 없다는 것을 알 수 있다. <br>
     최종 데이터셋은 긍정적인 리뷰 26,401개와 부정적인 리뷰 9,250개로 구성되어 있으며, 긍부정 비율은 여전히 부정적인 리뷰에 비해 긍정적인 리뷰가 3배 가까이 높은 비율을 차지하고 있다.
     <hr>

   * ### 학습과 검증 데이터셋 분리
     
     전체 데이터셋을 학습과 검증 데이터셋으로 분리했다.
     학습 데이터셋은 모델의 학습에 사용되고, 검증 데이터셋은 학습된 모델의 성능을 평가하는 데에 활용된다.
     이를 통해 모델의 성능을 높이고 새로운 데이터에 대한 예측 능력을 향상시킬 수 있다.

     긍정적인 리뷰와 부정적인 리뷰를 각각 1,500개씩 뽑아 총 3000개의 데이터셋을 만들었으며, 그중 학습 데이터는 2400개, 검증 데이터는 600개로 분리하였다.

     <table>
      <tr><th align="center" colspan='6'>데이터셋 분리</th></tr>
      <tr><th>긍정</th><td>1500</td><th rowspan='2'>데이터셋</th><td rowspan='2'>3000</td><th>학습</th><td>2400</td></tr>
      <tr><th>부정</th><td>1500</td><th>검증</th><td>600</td></tr>
     </table>
     

     |   | review | label |
     |---|---|---|
     |0|모양이 마음에 들어 구입했는데 볼너비가 작아 구두방에서 원 들여 수...|0|
     |1|화면에서 보는것과는 다른 핏이에요 길이도 더 짧고 표면에 튄곳이 몇...|0|
     |...|...|...|
     |2998|진짜 이거 데님의 혁명인듯 착용감이 완전 편한데 디자인도 색상도...|1|
     |2999|완전 편해요구김걱정 없이 편안하고 시원햐서이 바지만 입게 되네요...|1|



<hr>


## 3. 재학습 결과
   * ### 개발 환경
     <a href="https://blog.jetbrains.com/pycharm/2023/03/2022-3-3/" target="_blank"><img src="https://img.shields.io/badge/PyCharm-2bc382?style=flat&logo=PyCharm&logoColor=white"/></a>
   <a href="https://www.python.org/downloads/release/python-3913/" target="_blank"><img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white"/></a>
   <a href="" target="_blank"><img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=flat&logo=PyTorch&logoColor=white"/></a>
   <a href="" target="_blank"><img src="https://img.shields.io/badge/NumPy-013243?style=flat&logo=NumPy&logoColor=white"/></a>
   <a href="" target="_blank"><img src="https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white"/></a>
   <a href="" target="_blank"><img src="https://img.shields.io/badge/transformers-409FFF?style=flat&logoColor=white"/></a>
   <a href="" target="_blank"><img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white"/></a>

 
   * ### 3.2 KoELECTRA fine-tuning

     Optimizer, batch size, epoch 수 등 fine-tuning을 위한 하이퍼파라미터를 설정하였으며, 학습 데이터로는 3000개의 1대1 긍부정 리뷰 데이터셋을 사용했다.

     
   * ### 3.3 학습 결과 그래프

     <p align="center" width="100%">
       <img width="49.5%" src="https://github.com/wnaely/Sentyle/assets/130523834/e86552af-540c-425c-b248-8d43a99fefbc">
     <img width="49.5%" src="https://github.com/wnaely/Sentyle/assets/130523834/e7a829cd-c0b6-4267-ac82-1ee9ecd14762">
     </p>

     <table>
       <tr align="center"><th colspan="2">결과</th><th>Epoch 1</th><th>Epoch 2</th><th>Epoch 3</th><th>Epoch 4</th></tr>
       <tr align="center"><th rowspan="2">학습데이터</th><td>평균 학습 오차</td><td>0.58</td><td>0.37</td><td>0.24</td> 
       <td>0.15</td></tr>
       <tr align="center"><td>검증 정확도</td><td>0.74</td><td>0.86</td><td>0.87</td><td>0.89</td></tr>
     </table>

     첫 번째 학습 단계에서 0.369의 놉은 loss값과 달리, 학습 단계가 진행될수록 loss 값이 감소하여 네 번째 단계에서는 0.029로 낮게 나타난다.
     정확도도 학습이 진행됨에 따라 증가하는 변화를 보인다. 초기에는 93% 이었지만 마지막 단계에서는 95.6%로 성능이 향상되었다.
     각각의 변화는 모델이 학습 데이터로부터 효과적으로 학습되었다는 것과 리뷰의 긍부정을 잘 예측하고 있다는 것을 나타낸다.

   * ### 3.4 모델 적용
     ```
     test steps :  1 Accuracy :  0.875
     test steps :  2 Accuracy :  1.0
     test steps :  3 Accuracy :  1.0
     ...
     test steps :  4455 Accuracy :  0.875
     test steps :  4456 Accuracy :  1.0
     test steps :  4457 Accuracy :  1.0
     Accuracy: 0.96
     test took: 1:56:41
     ```
     전체 데이터에 모델을 적용한 결과 긍부정 예측 정확도가 0.96%로 높게 나왔다.

<hr>

## 4. 마무리
이번 프로젝트를 진행하면서 KoELECTRA 모델을 활용하여 패션 쇼핑몰 리뷰의 긍부정을 예측하는 모델을 개발하였으며, 이 과정에서 한국어 리뷰의 자연어 처리와 감성 분석에 대한 이해와 실전 경험을 쌓을 수 있었다.<br>
영문 리뷰가 아닌 실제 한글 리뷰 데이터셋을 이용하여 분석하며 영문 리뷰의 분석 과정과는 다른 측면에서 더 관심 있게 프로젝트를 진행할 수 있었다.

데이터를 효과적으로 전처리하고 모델의 fine-tuning하는 과정이 모델의 학습에 큰 영향을 주는 요소임을 깨달았다. 
데이터의 품질과 구조와 모델의 하이퍼파라미터 설정, 학습 데이터의 분포와 양, 그리고 적절한 손실 함수 등을 고려하는 것이 모델의 성능에 직접적인 영향을 미치는 것을 확인하였고, 다음 번 프로젝트에서는 더욱 세부적인 전처리와 fine-tuning 과정을 진행하여 더 높은 성능의 모델과 결과를 얻는 것이 추가적인 목표이다.

<hr>
       
       
   ## References
   [01] https://www.dailypop.kr/news/articleView.html?idxno=65004 <br>
   [02] https://www.wiseapp.co.kr/insight/detail/408 <br>
   [03] https://www.m-i.kr/news/articleView.html?idxno=830313<br>
   [04] https://huggingface.co/monologg/koelectra-small-discriminator <br>
   [05] https://aws.amazon.com/ko/blogs/tech/kurly-sagemaker-product-review-classification-model/ <br>
   




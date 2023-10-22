![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=250&section=header&text=Sentyle&fontSize=80&animation=fadeIn&fontAlignY=35&descSize=15&desc='Sent'iment%20and%20S'tyle'&descAlignY=50&descAlign=43&fontColor=FFFFFF)


# 👟👜 Sentyle 👚👖
KOELECTRA를 활용하여 패션 쇼핑몰 리뷰 데이터 감성 분석 및 긍부정 예측

## 1. 개요

   * ### 문제정의
 
     현재 우리는 인터넷을 통해 언제 어디서나 쉽게 상품을 구매할 수 있다. 이러한 형태의 상거래를 전자상거래(e-commerce)라고 한다.
     
     <a href="https://www.samsungpop.com/mobile/invest/poptv.do?cmd=fileDown&FileNm=uma_200626.html"><img width="600" alt="e-commerce" src="https://user-images.githubusercontent.com/130523834/235652059-dfc61816-33cc-47cd-8ff4-28ed1d4ec2d1.jpg"> <br>
     (출처: 삼성증권 포트폴리오전략팀<sup>[01]</sup>) 
  
       <hr>



## 1.1 문제 정의
영화 리뷰는 영화 감상에 있어 가장 보편적으로 활용되는 정보의 창구이다.
- 영화 리뷰와 영화 흥행의 상관관계를 나타내는 참고자료를 통해 영화 리뷰의 가치를 언급
- [[1]](링크) 등의 표기를 문장 뒤에 활용하여 참고 문헌을 작성할 것
- 프로젝트로 해당 과업을 해결할 때 기대할 수 있는 장점, 활용 가능성 등을 언급
- 필요에 따라서는 적절한 그림을 그려 표현(ppt 등)

## 1.2 데이터 및 모델 개요
데이터는 네이버에서 제공하는 영화 리뷰를 활용[2]하여, 총 20만 건의 데이터에 대해서 사전 학습 언어 모델의 재학습(fine-tuning)을 수행한다.

| 입력 |모델|출력|
|----------|---|---|
| 영화 리뷰 문장 |KOELECTRA small[3]|부정(0), 긍정(1)|

영화 리뷰 문장은 전처리를 통해서 가공한다. 대표적인 전처리로는 결측치와 중복값을 제거하고, 띄어쓰기로 구분이 되지 않는 리뷰 역시 제거한다.

# 2. 데이터
## 2.1 데이터 소스

## 2.2 탐색적 데이터 분석

## 2.3 데이터 전처리
- 입력 데이터의 전처리 과정
- 학습에 활용할 데이터의 양
- 학습과 검증 데이터셋 분리
- 학습 데이터의 구성


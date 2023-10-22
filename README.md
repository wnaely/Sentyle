![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=300&section=header&text=Sentyle&fontSize=80&animation=fadeIn&fontAlignY=36&descSize=25&desc=Prediction%20of%20positive%20and%20negative%20Amazon%20user%20reviews&descAlignY=53&fontColor=FFFFFF)


# Sentyle
패션 쇼핑몰 리뷰 데이터 감성 분석 및 긍부정 예측
<hr>

# 1. 개요
이번 프로젝트에서는 한국어 자연어 처리 모델인 KOELECTRA를 활용하여 네이버 영화 리뷰의 긍부정 예측을 하고자 한다.

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


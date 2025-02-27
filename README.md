이해를 위해 참고한 사이트 목록이다.
1.  [Transformer Explainer: LLM Transformer Model Visually Explained](https://poloclub.github.io/transformer-explainer/)
2.  [The Illustrated Transformer](https://nlpinkorean.github.io/illustrated-transformer/)
3.  [(18-01 트랜스포머 완전 정복)](https://wikidocs.net/217018)
4.  [\[NLP 논문 구현\] pytorch로 구현하는 Transformer (Attention is All You Need)](https://cpm0722.github.io/pytorch-


### 시작
RAG 라는 공부를 시작하면서 자연스레 LLM에 관심이 가기 시작하였고 어느 순간부터 RAG에 대해 이해가 가질 않았다. Tokenization, Embedding, Text Splitter 이라는 문장들이 헷갈리기 시작하면서 어려움이 찾아와 LLM의 기초가 되는 Transformer 아키텍처에 대해 이해해보기로 하였다.
초반이라 내용이 적고 빈틈 투성이일 수 있으나 차차 채워가도록 하겠습니다.

위에 사이트 및 "Attention is all you need" 논문을 참고하였다.

### Transformer 란?
2017년에 발표된 "Attention is All You Need" 논문에서 Transformer 아키텍처는 기존의 RNN이나 LSTM과 같은 순차적 처리 방식을 사용하던 모델들과 달리 Self-Attention 메커니즘을 통해 입력 시퀀스의 모든 단어 간의 관계를 동시에 고려할 수 있게 하였습니다. 이로 인해 학습 및 추론 시 병렬 처리가 가능해져 속도가 크게 향상되었으며 성능 또한 기존 모델들을 능가하게 되어 현재 LLM 개발에 활용되고 있다.

-------

## 1. 인코더 (Encoder)

인코더는 두 개의 층으로 구분됩니다: 셀프 어텐션(Self-Attention)과 피드 포워드 신경망(Feed Forward Neural Network)입니다.

### 1.1 멀티 헤드 셀프 어텐션 (Multi-Head Self Attention)

어텐션(attention) 연산은 다음과 같이 정의됩니다:

Word Embedding 및 Position Encoding이 적용된 다차원 벡터 (n, $d_{dim}$) 형태의 입력을 생성합니다. 이를 편의상 D라고 하겠습니다. D는 하이퍼파라미터인 num_head 값에 따라 나누어집니다. 논문에서는 num_head = 6으로 설정되었습니다.

### 1.2 Position-Wide Feed Forward Neural Network


## 2. 디코더 (Decoder)


### 2.1 Masked Multi-Head Self Attention


### 2.2 Multi-Head Attention


## 3. FC Layer (Fully Connected Layer)


## 4. Add & Norm

### 4.1 Residual Connection

### 4.2 Layer Normalization



- 구글이 2017년 발표한 Attention All you need" 라는 논문이다.  기존 seq2seq 방식은 순차적인 처리이지만 Transformer는 인코더-디코더 방식을 유지하면서 병렬 처리가 가능하다.

- 내가 본 Transformer 는 크게 n가지로 구성되어 있다.
1. Embedding
	1. Word Embedding
	2. Postional Encoding
2. Encoder
	1. Encoder Block
		1. Multi-Head Self Attention
		 - $Attention(Q,K,V) = softmax(\frac{QK^T}{\sqrt{d_k}})V$
		 - Q :  Query, K = Key, V = Value
		 - 멀티 헤드 셀프 어텐션은 모든 키 값에 대해 계산을 수행한다. 
		 - 입력의 차원을 하이퍼 파라미터인 num_head에 따라 num_head개로 나눠서 계산을 수행 후 concat 한다.
		2. Position Wide Feed Forward Neural Network
3. Decoder
	1. Masked Multi-Head Self Attention
		- 디코더의 경우 입력의 길이가 인코더 출력의 길이랑 같아야 한다. 이로 인해 빈 부분에 `<pad>` 라는 토큰을 넣어 값을 무시하도록 아주 작은 수를 더해준다.
	2. Multi-Head Attention
		* 셀프 어텐션이 아닌 그냥 어텐션이다. Q값의 경우 인코더의 출력, K,V는 디코더의 값을 받아 연산을 수행한다.
4. FC Layer (Linear)
	- 가중치를 곱하거나 더해주는 레이어이다.
5. Postion Wide Feed Forward Nueral Network
	* 입력 차원을 증폭하여 신경망에 데이터를 입력 후 가중치 및 편항을 더해 출력하여 준다.
6. Add&Norm
	1. Residual Connection
		- 전치 연결이라고 한다. 포지셔닝 인코더 백터와 멀티 헤드 셀프 어텐션이 끝난 출력값을 더해주는 단계이다.
	2. Layer Normalization
		- ... 기억이 나지 않는다. 재공부 후 수정 필요

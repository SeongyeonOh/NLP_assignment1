# NLP_assignment1
이 모델은 이전의 seq2seq모델의 디코더에서 매 time step (t) 마다 인코더의 전체 문장에 대한 정보를 계속 가지고 있어야 하는 문제점을 개선하기 위한 모델이다.

### Attention
attention이라는 방식을 통해 인코더의 문장들 중 디코더의 현재 t 시점의 단어를 예측하는데 가장 관련이 큰 단어에 집중하는 효과를 얻는다. 그 방법은 아래와 같다.
1. source 문장의 길이와 동일한 길이의 attention vector a를 계산한다. a는 각 element가 0~1 사이고 모든 element의 합은 1이다.
2. source 문장의 hidden state H의 weighted sum을 계산해 weighted src vector (w)를 얻는다.
3. 매 디코딩 t 마다 새로운 w를 계산한다.


## CTRL: A Conditional Transformer Language Model for Controllable Generation

- link: https://arxiv.org/abs/1909.05858
- 특정 task or style 에 대한 Generation을 할 때, controllable하게 할 수 있게끔 하는 Transformer 기반 language model. 
- 이때 Controllable code를 줌으로써 속성에 맞는 Generation을 하게끔 한다.
  - 같은 제시어(anarchism)를 주었지만 Controllable Code (빨간색)를 다르게 주자, 결과가 다르게 나타남
  - ![image](https://user-images.githubusercontent.com/45448731/171433316-97f915d6-c3cd-435b-9776-5197d0aab4f0.png)

- 중복 문자열 생성을 피하기 위하여 이전에 생성된 토큰에 대해서는 패널티를 줄 수 있음
  - theta가 1.2정도 일때가 적당했음
  - inference시에만 사용함
  - ![image](https://user-images.githubusercontent.com/45448731/171435214-2764609a-9bdb-4e5e-8119-4c42e682b05b.png)
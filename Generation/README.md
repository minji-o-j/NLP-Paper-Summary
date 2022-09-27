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





------

## Neural Text Generation with Unlikelihood Training 

- ICLR 2020
- link: https://arxiv.org/abs/1908.04319
- Generation을 할 때 Maximize log-likehood를 사용하여 학습하는 것은 원하지 않는 토큰이 생성되는 것에 대하여 penalty를 주지 않기 때문에 문제가 있음
- Unlikelihood Training 제안
  - Unlikelihood Training
    - 원하지 않는 특정 토큰 (**negative candidates**) 를 줄이는 것을 목적으로 함
    - ![image](https://user-images.githubusercontent.com/45448731/172748560-686c6c7f-207f-4f3b-b90e-c6f66f0e3f23.png)
  - Sequence-Level Unlikelihood Training
    - Decoded된 문장에 negative candidates를 넣고 token에 페널티를 줌
    - ![image](https://user-images.githubusercontent.com/45448731/172748534-c7a47448-f458-4d13-aaa6-16664396cec8.png)



---

## FUDGE: Controlled Text Generation With Future Discriminators

- NAACL 2021

- link: https://aclanthology.org/2021.naacl-main.276/

- code: https://github.com/yangkevin2/naacl-2021-fudge-controlled-generation

- large language model에 특정 속성 α를 적용시키려 할 때 **재학습 or data fine-tuning하지 않고 속성을 적용하는 법**에 대한 연구

- Model

  ![image-20220830121007757](C:\Users\Minji\AppData\Roaming\Typora\typora-user-images\image-20220830121007757.png)

  - 남색 블럭: 다음 토큰 예측(기존 language generate model decoder)
  - 빨간 블럭: 속성 α가 미래에 나타날 것인가에 대한 binary classifier
    - 남색 블럭에서 나온 결과에 대한 확률(do you want, do you prefer, do you thus, ...)
  - 두 확률의 곱이 높은 토큰이 x3이 된다



---

## The EOS Decision and Length Extrapolation

- BlackboxNLP 2020 (EMNLP)
- link: https://aclanthology.org/2020.blackboxnlp-1.26/
- train data보다 긴 길이의 문장을 생성할 때(외삽) task에서의 성능 평가
- test에서 generation시 문장을 계속해서 생성하다가, length oracle(실제 ground truth의 길이만큼 자름)
  - ![image](https://user-images.githubusercontent.com/45448731/192455217-f404190f-f7fe-498e-aab4-a362099598d5.png)
- train에서 EOS 토큰을 학습시킬 경우 (+EOS)보다 학습시키지 않을 경우 (-EOS)의 성능이 더 좋았음 
- 아직 잘 모르겠는 것 (찾고자 하는 내용과 논문이 거리가 멀어서 패스함):
  - ![image-20220927160239412](C:\Users\Minji\AppData\Roaming\Typora\typora-user-images\image-20220927160239412.png)


---

## Don't Say That! Making Inconsistent Dialogue Unlikely with Unlikelihood Training

- ACL 2020
- link: https://aclanthology.org/2020.acl-main.428/





---

## Learning to summarize with human feedback

- NeurIPS 2020
- link: https://proceedings.neurips.cc/paper/2020/file/1f89885d556929e98d3ef9b86448f951-Paper.pdf
- 강화학습

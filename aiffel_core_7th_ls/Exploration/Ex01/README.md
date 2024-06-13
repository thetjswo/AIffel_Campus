# [Exploration-EX01] Repository

<Exploration 01> 모듈에서 진행한 메인퀘스트 레포지토리

---

## 파일 구성

1. Project_Ex01.Flowers
   - 노드를 학습후 
      - basic CNN 모델 학습 
      - ResNet50 V2 모델 구현
      - MobilenNet V2 모델 구현

---

## Code Peer Review
**Coder** : 이슬 <br>
**Reviewer** : 조수민  

- [O]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 부분의 코드 및 결과물을 근거로 첨부  
 <br>  <br>  
```
# Create the conv base from the pre-trained ResNet50 V2
IMG_SHAPE = tuple(IMG_SIZE) + (3,) # 이렇게도 차원을 추가할수 있다니?!
conv_base = tf.keras.applications.ResNet50V2(input_shape=IMG_SHAPE,
                                               include_top=False,  # for only feature extraction
                                               weights='imagenet')
conv_base.trainable=False
conv_base.summary()

# 이하 생략

# load model
resnet50_model = tf.keras.models.load_model('resnet50_v2')
resnet50_model.summary()
# evaluate resnet50 model
evaluation_results = model.evaluate(test_batches)
print("Loss:", evaluation_results[0])
print("Metrics:", evaluation_results[1:])
``` 

- **조수민:ResNet과 MobileNet을 비교해보며 진행하였던 점이 인상깊었고 결과물 첨부 확인**  
<br>  

- [O]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
<br>  
**조수민:주석 및 텍스트가 중간중간 적혀있어서 어떠한 이유로 코드를 작성했고 코드 작성 방향을 적어두었다. 또한 어느 부분에서 막혔는지, 어떤 시도를 하였는지 알 수 있었다.**   
<br>  

- [O]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인 또는
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
<br>  
**조수민:앞서 말했듯이 막혔던 부분이 모두 기록 되어 있어서 어떤 시도를 했는지까지 알 수 있었다.**   
<br> 
- [ O]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 상세히 기록되어 있는지 확인
        - 딥러닝 모델의 경우,
        인풋이 들어가 최종적으로 아웃풋이 나오기까지의 전체 흐름을 도식화하여 
        모델 아키텍쳐에 대한 이해를 돕고 있는지 확인
<br>  
**조수민: summary 밑 회고 작성이 잘 되어있다.**   
<br> 
- [O ]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 모듈화(함수화) 했는지
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
<br>  
**조수민: 효율적으로 작성되어있다!**   
<br> 

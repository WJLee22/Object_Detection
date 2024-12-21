# 객체 탐지 by TensorFlow Lite in Android: Kotlin
> `TensorFlow Lite`: 파이썬 텐서플로우의 경량화버전  
> so, 모바일 및 임베디드 기기에서 머신러닝 모델을 실행하기에 최적화

> 객체 탐지(Object Detection)는 이미지 및 비디오 내에서 유의미한 특징 객체를 탐지하는 작업   

> 특정 객체를 탐지하여 경계 상자(Bounding Box)로 구분해낼 뿐만아니라, 이미지 분석을 통해 각 객체가 어떤 클래스에 속하는지 분류(ex. 마우스, 책, 사과...)

> +모델이 예측(추론)한 결과에 대한 신뢰도를 숫자로 표시 (0에서 1 사이의 값)

<br>

#### 본 testing 에서는, 직접 데이터를 수집하고 학습시켜 만든 탐지모델이 아닌 미리 학습된 모델(pre-trained model)을 사용하여 진행  
> pre-trained model 처리 절차

1. pre-trained 객체탐지 모델 로드(.tflite file)
2. 기기 카메라의 실시간 프레임 캡처
3. 모델이 캡쳐 이미지를 전처리
4. 객체 추론 실행 (모델을 사용하여 예측 수행)
5. 결과 후처리
6. 화면에 결과 표시 (경계 상자로 객체별 구분 & 객체 종류 표시 & 신뢰도 점수)

<br><br><hr>

# 실제 안드로이드 기기를 통한 testing     
> 데스크탑에 USB 연결 후, Android Studio를 통해 빌드 & 실제 기기에서 디버깅하여 테스팅하였음

<br>


#### 각 객체 Bounding Box 내의 숫자는 객체 탐지 모델이 예측한 `신뢰도 점수` (Confidence Score)
> ex) "mouse 0.61"은 모델이 해당 객체를 마우스로 인식할 확률이 61%
<br>

![objectDetect](https://github.com/user-attachments/assets/2e1b6e25-b754-479f-9655-b1e3a60ebabd)
![objectDetect2](https://github.com/user-attachments/assets/d5a29a0c-db25-4420-944d-28a835c06abe)

<br><br><br><hr>

## 🚫environment Settings

### 1.Gradle JDK version
> Gradle JDK version must be "17"

![Gradle버젼17로맞춰줘야JVM21에러해결됨](https://github.com/user-attachments/assets/3256a797-5daf-4aba-9332-7b9600822c14)

<br><br>

### 2.Java & Kotlin JDK version
> set Java & Kotlin's compile version as same(ex. 17 version) 

![image](https://github.com/user-attachments/assets/da165877-0f1a-4ac3-8844-178d3e5bb60c)

<br><br>

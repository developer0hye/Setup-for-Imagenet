# 설치

이미지넷 데이터셋 설치 방법으로는 크게 두 가지 방법이 있습니다.

각 방법에는 설치 속도에 차이가 있으므로 환경에 따라 적합한 방법을 택해서 진행하시길 바랍니다. 

**첫 째**, [공식 홈페이지](http://www.image-net.org/challenges/LSVRC/2012/nonpub-downloads) 에서 설치할 수 있습니다.

![default](https://user-images.githubusercontent.com/35001605/52109318-6d002800-2640-11e9-8138-c478c94da897.png)


Test images 는 LSVRC 2012 대회가 열렸을 당시에 대회에 **제출된 모델**에 대한 성능 평가를 위한 데이터셋으로 이에 대한 Label 을 따로 공개하지 않기 때문에 Test images 에 대한 성능 검증이 불가능합니다. 따라서 Test images 는 다운로드 받지 않아도 됩니다. 

이러한 이유로 많은 CNN(Convolutional Neural Network) 연구들이 Validation images 를 이용하여 성능 평가를 하는 것을 확인할 수 있습니다.

**VGG**

![vgg2](https://user-images.githubusercontent.com/35001605/53281180-9a378600-3767-11e9-95d4-d0b6fe751d3a.png)

**RESNET**

![resnet2](https://user-images.githubusercontent.com/35001605/53281175-9146b480-3767-11e9-89e0-fa8ea75f925c.png)

**DENSENET**

![densenet2](https://user-images.githubusercontent.com/35001605/53281173-8e4bc400-3767-11e9-8938-c27190f6c0e0.png)

따라서 Train images 를 통해 모델에 대한 학습을 수행하고 Validation images 로 평가를 수행하면 됩니다.


**둘 째**, [토렌트](http://academictorrents.com/collection/imagenet-2012) 를 이용해서 설치할 수 있습니다.

홈페이지에 접속한 후 파란색 박스로 강조된 영역을 클릭합니다.

![default](https://user-images.githubusercontent.com/35001605/52109801-0714a000-2642-11e9-98ba-eaa6359ce709.png)

체크를 한뒤 Download 버튼을 누르면 설치가 진행됩니다.

![1](https://user-images.githubusercontent.com/35001605/52569830-626e3b80-2e55-11e9-91a2-16ac0684a89a.png)

![2](https://user-images.githubusercontent.com/35001605/52110952-a1c2ae00-2645-11e9-8c57-0209ab5f060c.png)


Training images 의 경우 용량이 100기가에 달하기 때문에 다운로드 받는데 오랜 시간이 걸릴 수 있습니다.

## 데이터 정리

Training set(Training images)과 Validation set(Validation images)을 설치하고 나면 아래의 파일들을 확인할 수 있습니다.

![files](https://user-images.githubusercontent.com/35001605/52572986-72d5e480-2e5c-11e9-9187-323fc0273f8c.PNG)

압축을 해제합니다. 이 때 Training set 의 경우 압축 파일 내부에 물체 종류별로 압축 파일이 존재하므로 모든 압축 파일을 해제하도록 합니다.

![train_files](https://user-images.githubusercontent.com/35001605/52573708-0e1b8980-2e5e-11e9-95a0-f6dc1b5c93d4.PNG)

모든 파일에 대해 압축을 해제하고 나면 데이터 셋은 다음과 같은 경로로 구성됩니다.

```
.../
  ILSVRC2012_img_train/
    n01440764/
      n01440764_18.JPEG
      .
      .
      .
      n01440764_32420.JPEG
     .
     .
     .
    n15075141/
      n15075141_27.JPEG
      .
      .
      .
      n15075141_53286.JPEG
      
  ILSVRC2012_img_val/
    ILSVRC2012_img_val_00000001.JPEG
    ILSVRC2012_img_val_00000002.JPEG
    ILSVRC2012_img_val_00000003.JPEG
    .
    .
    .
    ILSVRC2012_img_val_00050000.JPEG
```

### Validation set 정리


# 설치

이미지넷 분류 데이터셋(ILSVRC 2012) 설치 방법으로는 크게 두 가지 방법이 있습니다.

각 방법에는 설치 속도에 차이가 있으므로 환경에 따라 적합한 방법을 택해서 진행하시길 바라며 데이터 셋의 용량이 100GB 에 달하다 보니 시간이 오래 걸릴 수 있습니다.

**첫 째**, [공식 홈페이지](http://www.image-net.org/challenges/LSVRC/2012/nonpub-downloads) 에서 설치할 수 있습니다.

![default](https://user-images.githubusercontent.com/35001605/52109318-6d002800-2640-11e9-8138-c478c94da897.png)

Test set 은 LSVRC 2012 대회가 열렸을 당시에 대회에 **제출된 모델**에 대한 성능 평가를 위한 데이터셋으로 이에 대한 Label 을 따로 공개하지 않기 때문에 Test set 에 대한 성능 평가를 할 수 없습니다. 따라서 Test set 은 다운로드 받지 않아도 됩니다. 

이러한 이유로 이미지넷 분류 데이터셋을 이용한 많은 CNN(Convolutional Neural Network) 연구들이 **Validation set** 을 통해 성능 평가를 하는 것을 확인할 수 있습니다.

### VGG

![vgg2](https://user-images.githubusercontent.com/35001605/53281180-9a378600-3767-11e9-95d4-d0b6fe751d3a.png)

### RESNET

![resnet2_down_2](https://user-images.githubusercontent.com/35001605/53281608-cf93a200-376e-11e9-9679-758ce8d59dc1.png)

### DENSENET

![densenet2_down_2](https://user-images.githubusercontent.com/35001605/53281568-1c2aad80-376e-11e9-9130-8fc38042be4a.png)

**둘 째**, [토렌트](http://academictorrents.com/collection/imagenet-2012) 를 이용해서 설치할 수 있습니다.

![default](https://user-images.githubusercontent.com/35001605/52109801-0714a000-2642-11e9-98ba-eaa6359ce709.png)

체크를 한뒤 Download 버튼을 누르면 설치가 진행됩니다.

![1](https://user-images.githubusercontent.com/35001605/52569830-626e3b80-2e55-11e9-91a2-16ac0684a89a.png)

![2](https://user-images.githubusercontent.com/35001605/52110952-a1c2ae00-2645-11e9-8c57-0209ab5f060c.png)

## 데이터 정리

모든 설치가 완료되면 아래의 파일들이 설치됨을 확인할 수 있습니다.

![files](https://user-images.githubusercontent.com/35001605/52572986-72d5e480-2e5c-11e9-9187-323fc0273f8c.PNG)

이 후, 각 파일의 압축을 해제합니다. 

Training set 의 경우 압축 파일 내부에 물체 종류 별로 압축 파일이 추가적으로 존재합니다. 이 파일들 또한 압축을 해제하도록 합니다.

![train_files](https://user-images.githubusercontent.com/35001605/52573708-0e1b8980-2e5e-11e9-95a0-f6dc1b5c93d4.PNG)

모든 파일에 대해 압축을 해제하고 나면 데이터 셋은 다음과 같은 경로로 구성됩니다.

```
../
  ILSVRC2012_img_train/
    n01440764/
      n01440764_18.JPEG ... n01440764_32420.JPEG
    .
    .
    .
    n15075141/
      n15075141_27.JPEG ... n15075141_53286.JPEG
      
  ILSVRC2012_img_val/
    ILSVRC2012_img_val_00000001.JPEG ... ILSVRC2012_img_val_00050000.JPEG
```

### Validation set 정리

Training set은 이미지에 대해 폴더 별로 Label 이 정리 되어있는 반면, Validation set의 경우 이미지에 대한 Label 이 분류되어 있지 않음을 확인할 수 있습니다. 

**Training set 예시**

![training set inside](https://user-images.githubusercontent.com/35001605/53282752-b2b39a80-377f-11e9-8083-dee42a57303e.PNG)

**Validation set 예시**

![validation set inside](https://user-images.githubusercontent.com/35001605/53282754-b515f480-377f-11e9-8495-aa84ad7c3ae1.PNG)


추후에 이를 이용할 때, 처리가 용이하도록 Validation set 또한 Training set 과 동일하게 이미지에 대해 폴더 별로 분류를 시켜주도록 하겠습니다.

분류 방법은 아래와 같습니다.

1. 본 repository 에 업로드 된 [Imagenet_val_setup.sh](https://github.com/developer0hye/Setup-for-Imagenet/blob/master/Imagenet_val_setup.sh) 을 설치합니다.

2. Imagenet_val_setup.sh 를 ILSVRC2012_img_val 폴더 내부로 이동시킵니다.

**파일 경로 예시**
```
../
  ILSVRC2012_img_val/
    ILSVRC2012_img_val_00000001.JPEG ... ILSVRC2012_img_val_00050000.JPEG
    Imagenet_val_setup.sh
```

3. Imagenet_val_setup.sh 를 더블 클릭하여 실행 혹은 cmd 창에서 실행시켜줍니다.

![sh run1](https://user-images.githubusercontent.com/35001605/53282877-68cbb400-3781-11e9-9b31-aa53b4b5f280.PNG)

![sh run2](https://user-images.githubusercontent.com/35001605/53282876-68cbb400-3781-11e9-86e7-e94a0173320b.PNG)

4. 정리가 완료될 때 까지 기다립니다. 생각보다 시간이 오래 소요됩니다. 느긋히 기다리며 다른 일을 하시면 됩니다.

5. Validation set 또한 각 이미지에 대하여 폴더 별로 분류 되었음을 확인할 수 있습니다. 끝.

![val_after_cleanining](https://user-images.githubusercontent.com/35001605/53282873-5baec500-3781-11e9-8c12-befceb819075.PNG)

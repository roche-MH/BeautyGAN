# BeautyGAN

### 简介

BeautyGAN: Instance-level Facial Makeup Transfer with Deep Generative Adversarial Network

官方网站：[http://liusi-group.com/projects/BeautyGAN](http://liusi-group.com/projects/BeautyGAN)

提供了论文和数据集，但是没有开源代码，也没有提供训练好的模型

### 复现效果

![](result.jpg)

### 使用方法

- Python3.6
- TensorFlow1.9

下载训练好的模型

- [https://pan.baidu.com/s/1wngvgT0qzcKJ5LfLMO7m8A](https://pan.baidu.com/s/1wngvgT0qzcKJ5LfLMO7m8A)，7lip
- [https://drive.google.com/drive/folders/1pgVqnF2-rnOxcUQ3SO4JwHUFTdiSe5t9](https://drive.google.com/drive/folders/1pgVqnF2-rnOxcUQ3SO4JwHUFTdiSe5t9)

新建文件夹`model`，将模型文件放于其中

`imgs`中包括11张无妆图片，以及9张有妆图片

默认对`imgs/no_makeup/xfsy_0068.png`进行上妆

```
python main.py
```

如果需要对其他人脸图片上妆，传入图片路径即可，推荐使用大小合适的正脸图片

```
python main.py --no_makeup xxx.xxx
```
--- 단점
위 result는 테스트에 적합한 이미지 였다 일반적인 사진을 넣었을떄 모델의 성능이 좋지 않은 모습을 확인하였다.
얼굴인식이 제대로 잘 안되는것 처럼 보임
![](https://github.com/roche-MH/BeautyGAN/blob/master/imgs/result/suji.PNG?raw=true)
그래서 위 문제를 해결하고자 전체 이미지에서 dlib.get_face_chip 를 사용하여 얼굴을 정렬하고 얼굴 사이즈만큼 이미지를 따왔다 따온 이미지를 모델에 넣었을때 성능이 더 좋아지는 것을 확인하였다.
![](https://github.com/roche-MH/BeautyGAN/blob/master/imgs/result/sujimakeup.PNG?raw=true

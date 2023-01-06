## Kocrnn OCR 모델
##### 학습 일자: 2023/01/03
##### 학습 담당자: 정주희
##### **학습 데이터셋**: AI hub 한국어 글자체 이미지 - 인쇄체(13만개) 
##### (train: 9만개, test: 2만개, validation: 2만개)  
##### **추가학습 데이터셋**: **저화질화시킨** AI hub 한국어 글자체 이미지 - 인쇄체(11만개) 
##### (train: 7만개, test: 2만개, validation: 2만개)  
버전: python 3.9.15 / tensorflow-gpu 2.5.0 / CUDA 11.2 / cuDNN 8.1.0 / Nvidia 그래픽 카드 7.5  
추가 환경 설치:  
```  
# anaconda env 생성
conda create -n ocr-tf2 python=3.9

# install tensorflow
pip install tensorflow-gpu==2.5.0
pip install tensorflow==2.5.0

# install pytorch
pip install torch===1.7.1+cu110 torchvision===0.8.2+cu110 torchaudio===0.7.2 -f https://download.pytorch.org/whl/torch_stable.html

# install lib for OCR
conda install -c anaconda pillow nltk natsort
conda install -c conda-forge fire python-lmdb

# install cv2 (선택)
conda install -c conda-forge opencv

# download Naver-OCR CODE
git clone https://github.com/clovaai/deep-text-recognition-benchmark.git
```

#### [학습 완료 후 파일 구조]
```  
  |--deep-text-recognition-benchmark # 클론해오기
    |--ocr_data
      |--train
      |--test
      |--validation
      |--get_images.py
      |--gt_test.txt
      |--gt_train.txt
      |--gt_validation.txt
    |--ocr_low_data
        |--train
        |--test
        |--validation
        |--get_images.py
        |--gt_test.txt
        |--gt_train.txt
        |--gt_validation.txt
    |--...
  |--kor_dataset
    |--aihub_data
      |--ocr
        |--images # 여기에 AIhub 인쇄체 이미지파일들 넣기
        |--printed_data_info.json # 라벨링 파일
      |--ocr_low
        |--images # 여기에 *저화질화된* 인쇄체 이미지파일들 넣기
        |--printed_data_info.json # 라벨링 파일
  |--saved_models
    |--TPS-ResNet-BiLSTM-CTC-Seed1111
      |--best_accuracy.pth
      |--best_norm_ED.pth
      |--log_dataset.txt
      |--log_train.txt
      |--opt.txt
  |--aihub_dataset.py
  |--...
```
##### 학습 결과: train_loss: 0.00073, best_accuracy: 99.812
##### 추가학습 결과: train_loss: 0.0013, best_accuracy: 99.773

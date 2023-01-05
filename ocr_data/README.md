## Kocrnn OCR 모델
##### 학습 일자: 2023/01/03
##### 학습 담당자: 정주희
##### **학습 데이터셋**: AI hub 한국어 글자체 이미지 - 인쇄체
##### (train: 9만개, test: 2만개, validation: 2만개)

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
    |--...
  |--kor_dataset
    |--aihub_data
      |--ocr
        |--images # 여기에 AIhub 인쇄체 이미지파일들 넣기
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

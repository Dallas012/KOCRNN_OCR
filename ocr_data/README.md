## Kocrnn OCR 모델
학습 일자: 2023/01/03  
학습 담당자: 정주희  
**학습 데이터셋**: AI hub 한국어 글자체 이미지 - 인쇄체  
(train: 9만개, test: 2만개, validation: 2만개)  

**[학습 완료 후 파일 구조]**  
  |--deep-text-recognition-benchmark # 클론해오기  
  &nbsp;&nbsp;&nbsp;|--ocr_data  
  &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;|--train  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--test  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--validation  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--get_images.py  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--gt_test.txt  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--gt_train.txt  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--gt_validation.txt  
     &nbsp; &nbsp;|--...  
  |--kor_dataset  
    &nbsp;&nbsp;&nbsp;|--aihub_data  
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--ocr  
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--images # 여기에 AIhub 인쇄체 이미지파일들 넣기  
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--printed_data_info.json # 라벨링 파일  
  |--saved_models  
    &nbsp;&nbsp;|--TPS-ResNet-BiLSTM-CTC-Seed1111  
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--best_accuracy.pth  
      &nbsp;&nbsp;&nbsp;&nbsp; |--best_norm_ED.pth  
      &nbsp;&nbsp;&nbsp;&nbsp; |--log_dataset.txt  
      &nbsp;&nbsp;&nbsp;&nbsp; |--log_train.txt  
      &nbsp;&nbsp;&nbsp;&nbsp; |--opt.txt  
  |--aihub_dataset.py  
  |--...  

**학습 결과: train_loss: 0.00073, best_accuracy: 99.812**  

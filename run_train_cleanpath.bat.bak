@echo off
cd /d D:\work\PaddleOCR

call C:\Users\asus\miniconda3\condabin\conda.bat activate paddleocr

set PYTHONPATH=D:\work\PaddleOCR

REM 只保留最必要的系统路径 + conda 路径，避免外部 cudnn 干扰
set "PATH=%CONDA_PREFIX%\Library\bin;%CONDA_PREFIX%\Scripts;%CONDA_PREFIX%\bin;%SystemRoot%\System32;%SystemRoot%;%SystemRoot%\System32\Wbem"

python tools/train.py -c configs/rec/PP-OCRv5/PP-OCRv5_mobile_rec.yml -o ^
 Train.dataset.data_dir=D:/ocr_data/data ^
 Train.dataset.label_file_list=[D:/ocr_data/data/train_list.txt] ^
 Eval.dataset.data_dir=D:/ocr_data/data ^
 Eval.dataset.label_file_list=[D:/ocr_data/data/val_list.txt] ^
 Train.loader.batch_size_per_card=4 ^
 Train.loader.num_workers=2 ^
 Eval.loader.batch_size_per_card=4 ^
 Eval.loader.num_workers=2 ^
 Train.sampler.first_bs=16 ^
 Optimizer.lr.learning_rate=0.00005

pause

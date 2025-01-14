# ObjectCounting

## Giới thiệu

ObjectCounting là dự án của Công ty Brycen VN và Logitem , nhằm mục tiêu xây dựng hệ thống tự động đếm số lượng sản phẩm trong nhà máy.

## Các Bước Thực Hiện

### Bước 1a: Chuẩn bị môi trường conda

```bash
pip install --upgrade pip
conda create -n objectcounting_env python=3.9
conda activate objectcounting_env
git clone https://github.com/Brycenvn/ObjectCountingTraining  # clone
cd ObjectCountingTraining
Install torch, torchvision base on YOUR CUDA VERSION # https://pytorch.org/
pip install -r requirements.txt  # install
Run python detect.py --weights yolov5s.pt --source data/images/bus.jpg # kiểm tra môi trường đã được cài đặt thành công
```

### Bước 1b: Nếu không muốn sử dụng conda, xài docker.

```bash
sudo docker pull ultralytics/yolov5:latest
sudo docker run --ipc=host -it --gpus all -v "$(pwd)"/rebar:/usr/src/datasets ultralytics/yolov5:latest
Run python detect.py --weights yolov5s.pt --source data/images/bus.jpg # kiểm tra môi trường đã được cài đặt thành công
```

### Bước 2: Chuẩn bị dataset 

- Download [dataset](https://drive.google.com/drive/folders/1N9SwvQ0cRwZWhkkW7O3D2gD17EboFB5y?usp=drive_link)
- Thay đổi đường dẫn nơi chưa dataset trong rebar.yaml

### Bước 3: Huấn luyện 

```bash
python train.py --img 640 --epochs 100 --data path_to_rebar.yml --weights yolov5s.pt
```

### Bước 4: Sử Dụng

- Sử dụng model đã được huấn luyện tại [Inference](https://github.com/Brycenvn/ObjectCountingInference)

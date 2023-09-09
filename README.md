# ObjectCounting

## Giới thiệu

ObjectCounting là dự án của Công ty Brycen VN và Logitem , nhằm mục tiêu xây dựng hệ thống tự động đếm số lượng sản phẩm trong nhà máy.

## Các Bước Thực Hiện

### Bước 1: Chuẩn bị môi trường

```bash
git clone https://github.com/Brycenvn/ObjectCountingTraining  # clone
cd ObjectCountingTraining
pip install -r requirements.txt  # install
```

### Bước 2: Chuẩn bị dataset 

- Download [dataset](https://drive.google.com/file/d/1-rRbIP2ds0zSjcI8j8o1ERm3ethAAiZr/view)
- Chuyển đổi theo yolo format.
- Thay đổi đường dẫn nơi chưa dataset trong [rebar.yaml](https://github.com/Brycenvn/ObjectCountingTraining/blob/master/data/rebar.yaml
)
### Bước 3: Huấn luyện 

```bash
python train.py --img 640 --epochs 100 --data data/rebar.yaml --weights yolov5s.pt
```

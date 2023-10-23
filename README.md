# SSD
Trying to solve the blood cell recognition problem on https://github.com/Shenggan/BCCD_Dataset using https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Object-Detection

## How to use
### Init Dataset
Put the path in ```create_data_lists.py``` where your dataset is located:
```python
from utils import create_data_lists

if __name__ == '__main__':
    create_data_lists(bccd_path='../a-PyTorch-Tutorial-to-Object-Detection/data/BCCD',
                      output_folder='../a-PyTorch-Tutorial-to-Object-Detection/data/BCCD')
```
### Start train
For train SSD model use:
```sh
$ python train.py
```
## Inference
You also can use trained model https://drive.google.com/file/d/1kngBgx_eGpzcUwwpRWwG21RGQEa0JbEE/view?usp=share_link

Just copy it to ```a-PyTorch-Tutorial-to-Object-Detection/```

In file ```detect.py``` youcan choose picture (```img_path```) for inference:
```python
if __name__ == '__main__':
    img_path = '../a-PyTorch-Tutorial-to-Object-Detection/data/BCCD/JPEGImages/BloodImage_00023.jpg'
    original_image = Image.open(img_path, mode='r')
    original_image = original_image.convert('RGB')
    detect(original_image, min_score=0.2, max_overlap=0.5, top_k=200).show()
```
## Example inference
After ~300 training steps:

![example_inference](https://github.com/Cashaqu/SSD/blob/main/a-PyTorch-Tutorial-to-Object-Detection/inference.PNG)

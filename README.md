# 动态纹理生成-计算机视觉
[github](https://github.com/guguguzi/dynamic-texture-synthesis)

## Requirements
- 运行环境：Python2.7, Tensorflow1.3
- 数据集：使用Dyntex数据集[点此下载](https://drive.google.com/file/d/1QupB8gBglM5orjCDCTli1VUchdGDgxTN/view?usp=sharing)
- Appearance-stream [tfmodel](https://drive.google.com/file/d/1gYIEP6kPIgHxWW465kQ_QiwVoQq9Mx7H/view?usp=sharing)

## 运行前准备
- 将预训练好的appearance-stream tfmodel 放入 `./models`.

## 使用说明

### 动态纹理生成
```
python synthesize.py --type=dts --gpu=<NUMBER> --runid=<NAME> --dynamics_target=data/dynamic_textures/<FOLDER> --dynamics_model=models/<TFMODEL>
```
#### 样例
```
python synthesize.py --type=dts --gpu=0 --runid="my_cool_fish" --dynamics_target=data/dynamic_textures/fish --dynamics_model=models/MSOEnet_ucf101train01_6e-4_allaug_exceptscale_randorder.tfmodel
```

### 动态纹理转换
```
python synthesize.py --type=dst --gpu=<NUMBER> --runid=<NAME> --dynamics_target=data/dynamic_textures/<FOLDER> --dynamics_model=models/<TFMODEL> --appearance_target=data/textures/<IMAGE>
```

### 生成首尾连接的动态纹理
```
python synthesize.py --type=inf --gpu=<NUMBER> --runid=<NAME> --dynamics_target=data/dynamic_textures/<FOLDER> --dynamics_model=models/<TFMODEL>
```

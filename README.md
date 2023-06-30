# Generalizable-NeRF
## 环境配置
Ubuntu 16.04

GTX2080ti 12g

pytorch 2.0.0

CUDA 11.8

## 训练和渲染
数据集和代码使用方式参考[GNT](https://github.com/VITA-Group/GNT)

### 训练

    python3 train.py --config configs/gnt_full.txt --N_rand 256

### 测试

    python3 eval.py --config configs/gnt_full.txt --expname gnt_full --chunk_size 500 --run_val --N_samples 192

### 渲染

    python3 render.py --config configs/gnt_llff.txt --eval_dataset llff_render --eval_scenes orchids --expname gnt_orchids --chunk_size 500 --N_samples 192

## 实验结果

<div align="center">

|      | PSNR | SSIM | LPIPS |
| ---------- | -----------| -----------| -----------|
| 论文结果(250000 iters) | 25.1711 | 0.1535 | 0.8309 |
| 复现结果(400000 iters) | 24.8690 | 0.1584 | 0.8344 |

</div>

## LLFF数据集制作
1. 用手机对一个静态场景拍摄20-30张照片，角度需有一定差异
2. 将图片放入colmap中计算相机参数
3. 将在colmap中计算得到的相机参数按照[LLFF](https://github.com/Fyusion/LLFF)制作LLFF格式的数据集

## 重建结果
渲染视频以及训练模型见网盘内avi文件和pth文件

[https://pan.baidu.com/s/1J9639OUo6p5D1wvR3L5t3w?pwd=4hhi]

提取码: 4hhi

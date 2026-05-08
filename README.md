## 
This is the code for the paper
Class-Enhanced Spatiotemporal Attention Modeling for Multi-Scale Human Motion Prediction
## Introduction
![Framework](images/framework.png)

### Dependencies

* cuda 11.4
* Python 3.8
* Pytorch 1.7.0

### Get the Data
We use two public datasets in this work:
- Human3.6M: https://paperswithcode.com/dataset/human3-6m
- CMU Mocap Dataset: http://mocap.cs.cmu.edu/

Directory structure: 
```shell script
h3.6m
|-- S1
|-- S5
|-- S6
|-- ...
`-- S11
```
Directory structure:
```shell script
cmu_mocap
|-- test
|-- train
```

Put the all downloaded datasets in ./datasets directory.

### Training
All running arguments are defined in [opt.py](utils/opt.py). Use the commands below to train on different datasets and representations.
To train,
```bash
python main_h36m_3d.py --kernel_size 10 --dct_n 20 --input_n 50 --output_n 10 --skip_rate 1 --batch_size 128 --test_batch_size 128 --in_features 66 --epoch 100
```
```bash
python main_cmu_mocap.py --kernel_size 10 --dct_n 20 --input_n 50 --output_n 10 --skip_rate 1 --batch_size 128 --test_batch_size 128 --in_features 75  --epoch 100
```

## Citation
This paper is currently under review for The Visual Computer. If you find this repo useful, please consider citing our paper:

```bibtex
@article{CMHAP,
  title={Class-Enhanced Spatiotemporal Attention Modeling for Multi-Scale Human Motion Prediction},
  journal={The Visual Computer}
}


### Acknowledgments
The overall code framework is adapted from [_History Repeats Itself: Human Motion Prediction via Motion Attention_](https://github.com/wei-mao-2019/HisRepItself) 

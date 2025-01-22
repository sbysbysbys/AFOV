# Installation
**Step 1.** Install [PyTorch and Torchvision](https://pytorch.org/get-started/previous-versions/)

```shell
conda create -n AFOV python=3.9
conda activate AFOV

## Optional: install cuda-11.3 in conda environment
# Install CUDA Toolkit 11.3.0 in https://developer.nvidia.com/cuda-11.3.0-download-archive
# conda install cuda -c nvidia/label/cuda-11.3.0 -c nvidia/label/cuda-11.3.1
# export CUDA_HOME=/usr/local/cuda-11.3
# export PATH=/usr/local/cuda-11.3/bin$:${PATH}
# export LD_LIBRARY_PATH=/usr/local/cuda-11.3/lib64:${LD_LIBRARY_PATH}

# we use torch.__version__='1.11.0+cu113'
conda install pytorch==1.11.0 torchvision==0.12.0 cudatoolkit=11.3 -c pytorch
``` 

**Step 2.** Install [Detectron2](https://github.com/facebookresearch/detectron2):
```
# python -m pip install 'git+https://github.com/MaureenZOU/detectron2-xyz.git'
python -m pip install 'git+https://github.com/facebookresearch/detectron2.git@v0.6'
# pip install git+https://github.com/cocodataset/panopticapi.git
```

**Step 3.** Install MinkowskiEngine:
```
conda install openblas-devel -c anaconda
git clone https://github.com/NVIDIA/MinkowskiEngine.git
cd MinkowskiEngine
pip install ninja
python setup.py install --blas_include_dirs=${CONDA_PREFIX}/include --blas=openblas
```

**Step 3.** For more detailed information, please refer to [FC-CLIP_INSTALL](https://github.com/bytedance/fc-clip/blob/main/INSTALL.md), [CAT-Seg_INSTALL](https://github.com/KU-CVLAB/CAT-Seg/blob/main/INSTALL.md), [SAN_INSTALL](https://github.com/MendelXu/SAN).
```
conda install pytorch-scatter -c pyg
pip install -r requirements.txt
pip install pointnet2_ops_lib/.

# for fc-clip
pip install git+https://github.com/mlfoundations/open_clip.git --prefer-binary
cd ov_segment/fc-clip/fcclip/modeling/pixel_decoder/ops
sh make.sh
```
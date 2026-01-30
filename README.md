## Installation
1. 在目录下建立一个名为ckpts的文件夹，下载huggingface中的模型文件到该文件夹。
2. 配置相关环境（注：最好采用较快的solver）
```
conda create -n unifolm-wma python==3.10.18
conda activate unifolm-wma

conda install pinocchio=3.2.0 -c conda-forge -y
conda install ffmpeg=7.1.1 -c conda-forge

git clone --recurse-submodules https://github.com/unitreerobotics/unifolm-world-model-action.git

# If you already downloaded the repo:
cd unifolm-world-model-action
git submodule update --init --recursive

pip install -e .

cd external/dlimp
pip install -e .
```
3. 在 configs/inference/world_model_interaction.yaml 中指定```data_dir```的正确路径和```dataset_and_weights```的结构。
## Model Checkpoints
| Model | Description | Link|
|---------|-------|------|
|$\text{UnifoLM-WMA-0}_{Dual}$| Fine-tuned on five [Unitree opensource dataset](https://huggingface.co/collections/unitreerobotics/g1-dex1-datasets-68bae98bf0a26d617f9983ab) in both decision-making and simulation modes. | [HuggingFace](https://huggingface.co/unitreerobotics/UnifoLM-WMA-0-Dual)|


# MoDL

PyTorch implementation of MoDL: Model Based Deep Learning Architecture for Inverse Problems (Not official!)

Official code: https://github.com/hkaggarwal/modl

![alt text](https://github.com/hkaggarwal/modl/blob/master/MoDL_recursive.png)

## Run in Colab
You can try the script in Google Colab:

<a target="_blank" href="https://colab.research.google.com/github/mcencini/MoDL_PyTorch/blob/master/tryme.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## Reference paper

MoDL: Model Based Deep Learning Architecture for Inverse Problems  by H.K. Aggarwal, M.P Mani, and Mathews Jacob in IEEE Transactions on Medical Imaging,  2018 

Link: https://arxiv.org/abs/1712.02862

IEEE Xplore: https://ieeexplore.ieee.org/document/8434321/

## Preparing the environment

We suggest to use a virtual environment (Python=3.8+).

To prepare the environment, from repository root folder run:

```
pip install light-the-torch && ltt install -r requirements.txt
```

## Dataset

The multi-coil brain dataset used in the original paper is publically available. You can download the dataset from the following link and locate in under the `data` directory, positioned in repository root folder.

**Download Link** : https://drive.google.com/file/d/1qp-l9kJbRfQU1W5wCjOQZi7I3T6jwA37/view?usp=sharing

You can download the data by running this command (assuming we are in the repository root folder):

```
mkdir data
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1qp-l9kJbRfQU1W5wCjOQZi7I3T6jwA37' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1qp-l9kJbRfQU1W5wCjOQZi7I3T6jwA37" -O data/dataset.hdf5 && rm -rf /tmp/cookies.txt
```

## Configuration file

The configuration files are in `config` folder. Every setting is the same as the paper.

Configuration files for K=1 and K=10 are provided. The authors trained the K=1 model first, and then trained the K=10 models using the weights of K=1 model.

## Train

You can change the configuration file for training by modifying the `train.sh` file.

```
scripts/train.sh
```

## Test

You can change the configuration file for testing by modifying the `test.sh` file.

```
scripts/test.sh
```

## Saved models

Saved models are provided.

K=1: `workspace/base_modl,k=1/checkpoints/final.epoch0049-score37.3514.pth` 

K=10: `workspace/base_modl,k=10/checkpoints/final.epoch0049-score39.6311.pth`

# COS484_Final_Project
This repository contains the code needed to replicate our experiments for our final project in COS 484 (Spring 2024 semester) at Princeton University. The objective of our project was to replicate and extend the original paper "Birds have four legs?! NumerSense: Probing Numerical Commonsense Knowledge of Pre-Trained Language Models."

To setup the conda environment, please take the requirements file and run as follows, replacing ```<env>``` with your environment name:

```
conda create --name <env> --file requirements.txt
```

Note that you may need to replace directory paths for models, tokenizers, and datasets (both ATOMIC and NumerSense) with your own local/server paths in order for the code to run properly. Our code was ran on the Della high performance computing cluster at Princeton University, with GPU access to a single Nvidia A100 (80 GB of VRAM memory). If you need to run the code without GPU access, please set the ```TrainingArguments``` parameter ```fp16=False```. If running on the Della server, our notebook code can be run using a Jupyter session, and declaring the following slurm commands (for GPU access):
```
--gres=gpu:1 --constraint=gpu80
```

To generate the submittable results files (for the NumerSense eval.ai leaderboard), please run the last cell of the noteboook, taking care to set the line ```test = core``` for the core results, and ```test = all``` for the adversarial results. 

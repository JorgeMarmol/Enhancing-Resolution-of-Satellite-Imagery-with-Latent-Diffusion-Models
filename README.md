
###  Peer Review Repository

This repository is provided **exclusively for peer-review purposes**.  
Its use, distribution, or modification for any other purpose is not authorized.  

- Some files are obfuscated in this version.  
- Upon acceptance, the full source code will be released without any obfuscation.  

###  System Requirements

- **Operating System:** Windows 10 Home, version 22H2, 64-bit  
- **Python:** 3.8  

###  Model Weights

The model weights are provided in the following google drive link: https://drive.google.com/drive/folders/1hdylDympPT7NJkCtZpFRvYj93KhbA_m_?usp=drive_link


### Example usage

Run the pipeline with:

```bash
python launcher.py --config_path configs/config.yaml --ckpt_path checkpoints/model.ckpt --input_size 320 --n_slides_generated 2 --ddim_steps 200 --ddim_eta 1.0
```

Input images must be placed in:

```bash
execution/inputs/
```
The generated output images will be saved automatically in:

```bash
execution/output/
```


###  Peer Review Repository

This repository is provided **exclusively for peer-review purposes**.  
Its use, distribution, or modification for any other purpose is not authorized.  

- Some files are obfuscated in this version.  
- Upon acceptance, the full source code will be released without any obfuscation.  

###  System Requirements

- **Operating System:** Windows 10 Home, version 22H2, 64-bit  
- **Python:** 3.8
- **Cuda:**: 11.7
  
### Create the environment

Option A Conda

```bash
conda env create -f environment.yml
conda activate ldm-sat
```

Option B Pip

```bash
python -m venv .venv
.venv\Scripts\activate            # Windows
pip install -r requirements.txt
```

## Dataset

The experiments in this work were conducted using satellite imagery from **GOES-16 (Geostationary Operational Environmental Satellite-16) FD Geocolor**.  
This dataset provides high temporal resolution images of the Earth, widely used in meteorology and environmental monitoring.  

- **Source:** NOAA GOES-16 full disk satellite data.  
- **Link to download:** https://noaa-goes16-imagery.s3.amazonaws.com/index.html.  


###  Model Weights

Download the file **`model.ckpt`** from the [Google Drive link](https://drive.google.com/drive/folders/1hdylDympPT7NJkCtZpFRvYj93KhbA_m_?usp=drive_link)  
and place it in the following folder:

```bash
checkpoints/
```

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

### Command-line parameters

- `--n_slides_generated`
Number of **intermediate images generated between each input pair**.
Example: `2` → generates two intermediate images.
  
- --`config_path`
Path to the YAML configuration file containing model and pipeline settings (e.g., hyperparameters, preprocessing options).
Example: configs/config.yaml.

- --`ckpt_path`
Path to the model checkpoint file (.ckpt) with pre-trained weights.
Example: checkpoints/model.ckpt.

- --`input_size`
Size to which each image will be resized.
Example: 320 (for the pretrained model provided the input size must be 320)

- --`ddim_steps`
Number of denoising steps in the DDIM sampling process.
Higher = better quality, but slower. Typical range: 50 – 500.
Example: 200.

- --`ddim_eta`
Stochasticity parameter for DDIM sampling. 0.0 → deterministic outputs. >0.0 → adds controlled randomness for diverse results.
Example: 1.0.




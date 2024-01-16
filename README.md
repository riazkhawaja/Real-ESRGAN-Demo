# Real-ESRGAN-Demo

Installation:  
Have anaconda or miniconda installed (recommended) or latest python version.  
Have git installed and in PATH.  
If your Nvidia GPU is compatiable with CUDA, please download that as well for much faster inference speeds. https://developer.nvidia.com/cuda-downloads  
  
Download the repository using git.  
```
git clone https://github.com/xinntao/Real-ESRGAN.git
cd Real-ESRGAN
```
Ensure you have pip installed and then add the packages you need.  
```
python -m ensurepip
pip install basicsr
pip install -r requirements.txt
python setup.py develop
```
Now, we are going to download the different weights. There is 2x upscale, 4x, another upscaler for anime, etc. This command is for windows.  
```
cd weights
curl -O -L https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth
curl -O -L https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.1/RealESRGAN_x2plus.pth
curl -O -L https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.2.4/RealESRGAN_x4plus_anime_6B.pth
```
Finally, head over to the root directory with the inference script and we can run inference images in the inputs folder. Replace -n argument with model name (RealESRGAN_x2plus, RealESRGAN_x4plus, RealESRGAN_x4plus_anime_6B, etc).  
```
cd ..
python inference_realesrgan.py -n RealESRGAN_x2plus -i inputs 
```
Outputs are going to be in the results folder.  

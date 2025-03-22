## How to try running the code on C3I windows PC

# Check GPU drivers
```
nvidia-smi
```

# Create and activate Virtual Environment
```
conda update conda
# Create a new environment named "myenv" with Python 3.11
conda create -n myenv python=3.11

# Activate the environment
conda activate myenv

#To deactivate
conda deactivate
```

# Install PyTorch with CUDA support
```
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
```

# Install opencv
```
conda install -c conda-forge opencv
pip install opencv-contrib-python
```

# Install everything except PyTorch (already installed) and basicsr (which may not be on the default channels). Also note that skimage==0.0 is just a placeholder for scikit-image
```
conda install -c conda-forge imageio matplotlib numpy pandas scipy scikit-image tqdm

```

# Install basicsr
If basicsr isn’t available on Conda or conda-forge, you can install it with pip inside your Conda environment:
```
pip install basicsr
```

# Patch basicsr
```
# File: basicsr/data/degradations.py
from torchvision.transforms.functional_tensor import rgb_to_grayscale

# File: basicsr/data/degradations.py
from torchvision.transforms.functional import rgb_to_grayscale

```


# Check PyTorch and other Dependencies

Check CUDA
```
python -c "import torch; print('PyTorch version:', torch.__version__); \
print('CUDA available:', torch.cuda.is_available()); \
print('GPU:', torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'None')"
```

Check other dependencies
```
python -c 'import imageio, matplotlib, numpy, cv2, pandas, scipy, skimage, tqdm; print("All good!")'

```


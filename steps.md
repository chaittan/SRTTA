# Install python 3.8 using windows installer and create venv

```
py -3.8 -m venv myenv
myenv\Scripts\activate
```
# Clone the Git repository

```
git clone https://github.com/DengZeshuai/SRTTA
```
Restart git after installing and/or add to path 

# Install Git for Windows (if not already installed)

# Follow the download and checkpoints instructions

# Install the modified requirements.txt
First install torch with cuda enabled
```
pip install torch==1.10.1+cu111 -f https://download.pytorch.org/whl/cu111/torch_stable.html
```

Then to avoud any issues install the compatible version of torchvision
```
pip install torchvision==0.10.1+cu111 -f https://download.pytorch.org/whl/cu111/torch_stable.html
```

Now install pip wheel and install the dependencies without build isolation
```
pip install wheel
pip install --no-build-isolation -r requirements.txt
```

The updated requirements.txt
```
basicsr==1.3.4.9
imageio==2.26.0
matplotlib==3.7.1
numpy==1.23.0
opencv_contrib_python==4.7.0.72
opencv_python==4.7.0.72
pandas==1.5.3
scipy==1.9.1
scikit-image
tqdm==4.65.0
```

#Run SRTTA 


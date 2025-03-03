
# Nvidia GPU Setting

## Install Driver 
### Find the recommended nvidia driver

```sh
ubuntu-drivers devices
```

### Install Driver
```sh
sudo apt install [recommended_version]
```

- To complete intall, `reboot the computer`
```sh
sudo reboot
```
## Install CUDA Toolkit

Find the proper version of CUDA in this [LINK](https://docs.nvidia.com/deeplearning/cudnn/backend/latest/reference/support-matrix.html)

- To install `CUDA.11.8` version in `Ubuntu18.04`,
```sh
# Download
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run

# Install CUDA
sudo sh cuda_11.8.0_520.61.05_linux.run
```
- After install window oppear, choose only `cuda-toolkit`

- Apply the CUDA
```sh
# Add the path of CUDA
vim ~/.bashrc # or /etc/profile (for all users)
export PATH="/usr/local/cuda-11.8/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-11.8/lib64:$LD_LIBRARY_PATH"

# Apply new ENV variable
source ~/.bashrc # or source /etc/profile
```

- To complete intall, `reboot the computer`
```sh
sudo reboot
```
- Finally, check the install is completed
```sh
python
>> import torch
>> print(torch.cuda.is_available())
>> print(torch.cuda.device_count())
>> exit()

# Check NVIDIA Driver
nvidia-smi

# Check CUDA version
nvcc -V
```

## Install CuDNN
- Download the CuDNN in this [LINK](https://developer.nvidia.com/rdp/cudnn-archive)

- After download the deb file,
```sh
sudo dpkg -i [deb_filename]
```

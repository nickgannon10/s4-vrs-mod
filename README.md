Maybe explore : Data Science Virtual Machine (DSVM) or NVIDIA GPU-Optimized VMI with vGPU driver

---

Source image details
Source image publisher
nvidia
Source image offer
ngc_azure_17_11
Source image plan
base-version-24_05_1-gen2

---

sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-driver-535 -y
sudo reboot
nvidia-smi

---

wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-ubuntu2204.pin
sudo mv cuda-ubuntu2204.pin /etc/apt/preferences.d/cuda-repository-pin-600
sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/3bf863cc.pub
sudo add-apt-repository "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/ /"

---

sudo apt update
sudo apt install cuda-toolkit-11-8 -y

---
echo 'export PATH=/usr/local/cuda-11.8/bin${PATH:+:${PATH}}' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-11.8/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}' >> ~/.bashrc
source ~/.bashrc

---
conda create -n s4_env python=3.9 -y
conda activate s4_env
pip install -r requirements.txt


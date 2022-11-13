#
# Ray node and worker images with custom tools
#

# Base image
FROM rayproject/ray:1.13.0-gpu

# Install Ubuntu tools
RUN sudo apt-get update && sudo apt-get install -y \
    build-essential vim \
    && sudo rm -rf /var/lib/apt/lists/* \
    && sudo apt-get clean

# Work directory where data is loaded
RUN mkdir code
WORKDIR code

# Install Python tools
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt && rm requirements.txt
RUN conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch

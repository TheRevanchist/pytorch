Bootstrap: docker
From: nvidia/cuda:9.2-cudnn7-devel-ubuntu16.04

%labels
Maintainer Ismail Elezi

%help
This container runs Tensorflow-GPU.
    
# Add CUDA to the path
ENV LD_LIBRARY_PATH $LD_LIBRARY_PATH:/usr/local/cuda/lib64
ENV CUDA_HOME /usr/local/cuda
    

%post
    # default mount points
    mkdir -p /scratch/global /scratch/local /rcc/stor1/refdata /rcc/stor1/projects /rcc/stor1/depts
    
    # NVIDIA driver mount points
    mkdir /nvidia /cuda
    touch /usr/bin/nvidia-smi

    # Install necessary packages
    apt-get update && apt-get install -y --no-install-recommends \
        vim \
        build-essential \
        gcc-multilib \
        libatlas-base-dev \
        libboost-all-dev \
        libhdf5-serial-dev \
        libprotobuf-dev \
        protobuf-compiler \
        libopenblas-dev \
        liblapack-dev \
        gfortran \
        libcurl4-openssl-dev \
        python-pip \
        python3-pip \
        pkg-config \
        python-dev \
        python3-dev \
        python-setuptools \
        python3-setuptools\
        python-opencv \
        python-tk \
        libjpeg-dev \
        libfreetype6 \
        libfreetype6-dev \
        zlib1g-dev \
        cmake \
        wget \
        cython \
        git
    apt-get clean

    # Update pip
    pip install --no-cache-dir --upgrade pip==9.0.3
    pip3 install --no-cache-dir --upgrade pip==9.0.3

    # Install TensorFlow-GPU
    export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.4.1-cp27-none-linux_x86_64.whl
    pip install --no-cache-dir --ignore-installed --upgrade $TF_BINARY_URL

    # Install python packages
    pip install --upgrade keras tflearn numpy nibabel h5py scikit-learn pandas scipy matplotlib ipykernel jupyter image PyYAML pillow easydict

    # Install TensorFlow-GPU
    export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.4.1-cp35-cp35m-linux_x86_64.whl
    pip3 install --no-cache-dir --ignore-installed --upgrade $TF_BINARY_URL

    # Install python packages
    pip3 install --upgrade tflearn numpy nibabel h5py scikit-learn pandas scipy matplotlib ipykernel jupyter

    pip3 --no-cache-dir install \
        Pillow \
        h5py \
        ipykernel \
        jupyter \
        matplotlib \
        numpy \
        pandas \
        scipy \
        sklearn

    python3 -m ipykernel.kernelspec
    apt-get -y update 
    apt-get -y upgrade

    pip3 install tqdm  \
                Augmentor  \
                virtualenv

    apt-get -y install python3-tk

    pip3 install foolbox
    apt-get install curl
    pip3 install requests
    pip3 install randomgen
    pip3 install scikit-image
    pip3 install opencv-python
    
    pip3 install adversarial-vision-challenge
    pip3 install torch torchvision
    pip3 install foolbox
    pip3 install requests
    pip3 install randomgen
    pip3 install scikit-image
    pip3 install opencv-python
    pip3 install tensorboard_logger


FROM datmo/keras-tensorflow:py35-gpu

WORKDIR /root/
RUN apt-get update && \
    apt-get --assume-yes install \
      wget \
      pkg-config \
      python \
      python-dev \
      python-pip \
      python-numpy \
      python-scipy \
      python-matplotlib \
      python-h5py \
      python-astropy \
      python-glue \
      python-six \
      libblas-dev \
      liblapack-dev \
      libssl-dev \
      gfortran && \
    pip install --user gwpy

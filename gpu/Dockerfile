FROM datmo/keras-tensorflow:gpu-py35-notebook
LABEL maintainer="Samuel Bernardo <samuelbernardo.mail@gmail.com>"

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

CMD ["/home/run_jupyter.sh", "--allow-root"]
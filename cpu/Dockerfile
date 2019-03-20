FROM datmo/keras-tensorflow:cpu-py35-notebook
LABEL maintainer="Samuel Bernardo <samuelbernardo.mail@gmail.com>"

WORKDIR /root/
# Hack: solve wrong tensorflow-gpu module installed from base image
RUN pip --no-cache-dir uninstall -y tensorflow-gpu && \
    pip --no-cache-dir install tensorflow
# Install addittional features
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
      glue-sprite \
      python-six \
      libblas-dev \
      liblapack-dev \
      libssl-dev \
      gfortran \
      git \
      tar && \
    apt-get clean && \
    pip --no-cache-dir install glue && \
    pip --no-cache-dir install -U scikit-learn && \
    pip install --user gwpy && \
    mkdir -p /notebooks /data && \
    wget -O /data/2019_braga_school_O1_dataset.tar.gz https://owncloud.ego-gw.it/index.php/s/nHXFIJrCvAoDWob/download && \
    tar xf /data/2019_braga_school_O1_dataset.tar.gz -C /data && \
    rm /data/2019_braga_school_O1_dataset.tar.gz

CMD ["/run_jupyter.sh", "--allow-root", "--notebook-dir=/notebooks"]

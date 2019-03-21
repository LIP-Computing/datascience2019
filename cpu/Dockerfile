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
      tar \
      unzip && \
    apt-get clean && \
    pip --no-cache-dir install glue && \
    pip --no-cache-dir install -U scikit-learn && \
    pip install --user gwpy && \
    mkdir -p /notebooks/data && \
    wget -O /notebooks/data/2019_braga_school_O1_dataset.tar.gz https://owncloud.ego-gw.it/index.php/s/nHXFIJrCvAoDWob/download && \
    tar xf /notebooks/data/2019_braga_school_O1_dataset.tar.gz -C /notebooks/data --strip-components=1 && \
    rm /notebooks/data/2019_braga_school_O1_dataset.tar.gz && \
    wget -O /notebooks/2019BragaSchool-gwhandson-master.zip https://cernbox.cern.ch/index.php/s/VSDpUpsavpmZR4A/download?x-access-token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkcm9wX29ubHkiOmZhbHNlLCJleHAiOiIyMDE5LTAzLTIxVDE5OjU1OjU2LjM1MzQyMzU5MiswMTowMCIsImV4cGlyZXMiOjAsImlkIjoiMTcwNTM0IiwiaXRlbV90eXBlIjowLCJtdGltZSI6MTU1MzE5MDczOCwib3duZXIiOiJ0ZGlhc2RvdiIsInBhdGgiOiJlb3Nob21lLXQ6NDIzMjQzMTI4MzY4MDA1MTIiLCJwcm90ZWN0ZWQiOmZhbHNlLCJyZWFkX29ubHkiOnRydWUsInNoYXJlX25hbWUiOiIyMDE5QnJhZ2FTY2hvb2wtZ3doYW5kc29uLW1hc3Rlci56aXAiLCJ0b2tlbiI6IlZTRHBVcHNhdnBtWlI0QSJ9.M4LrY4oeQxT2mAQXFKoD3JCEAUGHRbOfixGbZ_KnrP8 && \
    unzip /notebooks/2019BragaSchool-gwhandson-master.zip -d /notebooks && \
    rm /notebooks/2019BragaSchool-gwhandson-master.zip

CMD ["/run_jupyter.sh", "--allow-root", "--notebook-dir=/notebooks"]

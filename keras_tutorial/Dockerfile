FROM python:3.6
LABEL maintainer="Samuel Bernardo <samuelbernardo.mail@gmail.com> & Giles Strong <giles.strong@outlook.com>"

WORKDIR /root/
# Install addittional features
RUN apt-get update && \
    apt-get --assume-yes install \
      wget \
      pkg-config \
      glue-sprite \
      python-six \
      libblas-dev \
      liblapack-dev \
      libssl-dev \
      gfortran \
      git \
      tar && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    pip --no-cache-dir install \
      glue \
      tensorflow==1.11.0 \
      keras==2.2.4 \
      notebook==5.4.1 \
      jupyter \
      matplotlib==3.0.2 \
      numpy==1.15.2 \
      pandas==0.23.4 \
      seaborn==0.8.1 \
      scikit-learn==0.20.0 \
      tornado==5.1.1 && \
    python -m ipykernel.kernelspec && \
    git clone https://github.com/parrt/random-forest-importances.git && \
    cd random-forest-importances/src && \
    pip install . && \
    jupyter notebook --generate-config --allow-root && \
    ipython profile create && \
    echo "c.NotebookApp.ip = '0.0.0.0'" >>/root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.port = 8888" >>/root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >>/root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.iopub_data_rate_limit=10000000000" >>/root/.jupyter/jupyter_notebook_config.py && \
    echo "c.MultiKernelManager.default_kernel_name = 'python3'" >>/root/.jupyter/jupyter_notebook_config.py && \
    echo "c.InteractiveShellApp.exec_lines = ['%matplotlib inline']" >>/root/.ipython/profile_default/ipython_config.py && \
    git clone https://github.com/GilesStrong/LIP_DSS_Keras_Tutorial_2019.git /notebooks && \
    mkdir /notebooks/notebooks/data && \
    wget -O /notebooks/notebooks/data/atlas-higgs-challenge-2014-v2.csv.gz http://opendata.cern.ch/record/328/files/atlas-higgs-challenge-2014-v2.csv.gz && \
    gunzip /notebooks/notebooks/data/atlas-higgs-challenge-2014-v2.csv.gz
ENV KERAS_BACKEND tensorflow
EXPOSE 8888

CMD ["jupyter","notebook", "--allow-root", "--notebook-dir=/notebooks"]

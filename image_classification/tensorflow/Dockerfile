FROM nvidia/cuda:9.0-cudnn7-runtime-ubuntu16.04


WORKDIR /research

RUN apt-get update

RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates \
    build-essential \
    git \
    python \
    python-pip
    

ENV HOME /research
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH


RUN apt-get install -y python-setuptools

RUN apt install --no-install-recommends python3-minimal python3   --yes --force-yes

RUN apt-get install -y python-pip python3-pip virtualenv htop --yes --force-yes
# RUN pip install --upgrade numpy scipy sklearn tf-nightly-gpu

RUN apt install python3-numpy python3-scipy --yes --force-yes



# Mount data into the docker
ADD . /research/resnet


WORKDIR /research/resnet
RUN pip3 install -r official/requirements.txt


ENTRYPOINT ["/bin/bash"]


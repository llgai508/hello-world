Bootstrap: docker
From: debian:stretch-slim
%labels
MAINTAINER Gao Wang, gaow@uchicago.edu
%post

cd /tmp

# Install dev libraries
apt-get update \
&& apt-get install -y --no-install-recommends \
curl \
unzip \
gzip \
bzip2 \
ca-certificates \
build-essential \
gfortran \
libgfortran-6-dev \
libgomp1 \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* /var/log/dpkg.log

# R, Python, SoS and DSC
MINICONDA_VERSION=4.5.11
PATH=/opt/miniconda3/bin:$PATH
curl https://repo.continuum.io/miniconda/Miniconda3-$MINICONDA_VERSION-Linux-x86_64.sh -o MCON.sh \
&& /bin/bash MCON.sh -b -p /opt/miniconda3 \
&& ln -s /opt/miniconda3/etc/profile.d/conda.sh /etc/profile.d/conda.sh \
&& conda install matplotlib==3.0.2 seaborn==0.9.0 \
&& conda install -c conda-forge r-base==3.5.1 sos==0.17.7 dsc==0.3.1.2 rpy2==2.9.4 \
&& conda clean --all -tipsy
%environment
export MINICONDA_VERSION=4.5.11
export PATH=/opt/miniconda3/bin:$PATH
export SuSiE_VERSION=8a4f7177c0031255901083fa0f62555307acb6d9
export R_ENVIRON_USER=""
export R_PROFILE_USER=""
export R_LIBS_USER=' '
export MKL_THREADING_LAYER=GNU
%runscript
echo "hello world from Lili"

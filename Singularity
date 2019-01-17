Bootstrap: docker
FROM: debian:9.3-slim
# Debian Stretch without manpages and other files
# usually not needed in containers.

%help

Contains R version 3.3.3.

%post

# Packages needed inside the container.
export CONTAINER_SOFTWARE="gfortran g++ gcc make libcurl3-gnutls"
## Set build variables.
# Packages needed only for the build process.
export BUILD_SOFTWARE="wget zlib1g-dev libbz2-dev liblzma-dev libpcre3-dev libcurl4-gnutls-dev"
# Needed for downloading source.
export R_BASE_URI="https://cran.r-project.org/src/base/R-3/"
export R_FOLDER_NAME="R-3.3.3"
export R_PACKAGE_NAME="${R_FOLDER_NAME}.tar.gz"
# Set paths to facilitate the build process.
export BUILDHOME="/tmp"

# Install build and run requirements.
apt-get update
apt-get install $BUILD_SOFTWARE $CONTAINER_SOFTWARE -y

# Get R Package
wget ${R_BASE_URI}${R_PACKAGE_NAME}
tar -xf $R_PACKAGE_NAME

# Build R
cd $R_FOLDER_NAME
./configure --with-readline=no --with-x=no
make
make install

# Removing installation overhead.
 
cd
rm -rf /tmp/*
apt-get purge $BUILD_SOFTWARE -y
apt-get autoclean -y
apt-get autoremove -y
rm -rf /var/lib/apt/lists/*

%test

# Can we call R?
R --version
I have no name!@data2:~/mysing$ 
I have no name!@data2:~/mysing$ 
I have no name!@data2:~/mysing$  
I have no name!@data2:~/mysing$ vi Singularity 
bash: vi: command not found
I have no name!@data2:~/mysing$ exit
gail01@data2: ~/mysing $ vi Singularity 

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
echo "helloworld from Lili"

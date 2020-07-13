# ren
sudo apt install -y gfortran git doxygen python-sphinx

sudo apt install -y python-numpy python-matplotlib python-pint ffmpeg subversion csh curl zlib*

tar zxvf openmpi-1.10.2.tar.gz

cd openmpi-1.10.2/

./configure --prefix=/public/home/user/openmpi --enable-mpi-thread-multiple --enable-orterun-prefix-by-default

make

make install




tar xvf hdf5-1.8.18.tar

cd hdf5-1.8.18/

./configure --prefix=/home/user/HDF5-serial

make

make install

make clean

CC=mpicc ./configure --prefix=/public/home/user/HDF5-parallel --enable-parallel # bash user

make

make install



export SMILEICXX=mpic++

export HDF5_ROOT_DIR=/home/astronomy/HDF5-parallel

export PATH=/home/astronomy/yt-conda/bin:$PATH

export PATH=/home/astronomy/openmpi/bin:$PATH

export PLUTO_DIR=/home/astronomy/PLUTO

export LD_LIBRARY_PATH="/home/astronomy/HDF5-serial/lib":$LD_LIBRARY_PATH

export LD_LIBRARY_PATH="/home/astronomy/HDF5-parallel/lib":$LD_LIBRARY_PATH

export LD_LIBRARY_PATH="/home/astronomy/openmpi/lib":$LD_LIBRARY_PATH

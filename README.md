# ren
sudo apt install -y gfortran git doxygen python-sphinx

sudo apt install -y python-numpy python-matplotlib python-pint ffmpeg subversion csh curl zlib*



https://www-lb.open-mpi.org/software/ompi/v1.10/

tar zxvf openmpi-1.10.2.tar.gz

cd openmpi-1.10.2/

./configure --prefix=/public/home/user/openmpi --enable-mpi-thread-multiple --enable-orterun-prefix-by-default

make

make install



https://portal.hdfgroup.org/display/support/HDF5+1.8.18

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



1. Install these packages

sudo apt-get install python-h5py ipython python-pint python-sphinx python-matplotlib python-dev  python-numpy

2. Since the system openmpi is not compiled with --enable-mpi-thread-multiple, a manual installation is required. Add the following lines to your ~/.bashrc or ~/.bash_profile file (You may choose any ${INSTALL_DIR})

export INSTALL_DIR=/usr/local
export PATH=${INSTALL_DIR}/openmpi/bin:${PATH}
export LD_LIBRARY_PATH=${INSTALL_DIR}/openmpi/lib:${LD_LIBRARY_PATH}
export PATH=${INSTALL_DIR}/hdf5/bin:${PATH}
export LD_LIBRARY_PATH=${INSTALL_DIR}/hdf5/lib:${LD_LIBRARY_PATH}
export HDF5_ROOT_DIR=${INSTALL_DIR}/hdf5

3.Restart your terminal

4.Download OpenMPI and install.

tar zxvf openmpi-*.*.*.tar.gz

cd openmpi-*.*.*

./configure --prefix=${INSTALL_DIR}/openmpi --enable-mpi-thread-multiple --enable-mpirun-prefix-by-default

make

sudo make install

5.Restart your terminal

6.Download HDF5 and install

tar zxvf hdf5-*.*.*.tar.gz

cd hdf5-*.*.*

./configure --prefix=${INSTALL_DIR}/hdf5 --enable-parallel --with-pic --enable-linux-lfs --enable-shared --enable-build-mode=production --disable-sharedlib-rpath --enable-static CC=mpicc FC=mpif90

make

sudo make install

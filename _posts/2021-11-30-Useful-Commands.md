---
title: Useful Commands
categories:
- Ideas
excerpt: |
  This post presents some useful commands for Linux, Python, MATLAB, C & Fortran.
feature_text: |
  ## Linux, Python, MATLAB, C & Fortran
  Try to make life easier
feature_image: "https://picsum.photos/2560/600?image=733"
image: "https://picsum.photos/2560/600?image=733"
---

<!-- more -->

* TOC
{:toc}

## Linux
#### Miscellaneous
```bash
# change mode
chmod +x filename    
# check history
history             
history | grep configure
# kill a progress
killall progress_name  
# output message to file
echo 'hello' > log
# combine figures in to a gif
convert -delay 10 -loop 0 input_*.png output.gif
# install packages
sudo dpkg -i XXX.deb
```

#### Slurm
```bash
# Check Partition
whichpartition
# Set MPI Environment on Hefei-HPC
module unload mpi/intelmpi/2018.4.274
module load   mpi/openmpi/2.1.2/gcc-7.3.1
```

#### Git
Setting
```bash
ssh-keygen -t rsa -C “your_Github_email@adrress”
cd ~/.ssh
vim id_rsa.pub
# and then copy the key into: Github website --> add Key
# check git ssh status 
ssh -T git@github.com  
# config     
git config --global user.name “your Github name”
git config --global user.email “your_Github_email@adrress”
```
Commit
```bash
git init
git add .
git commit -m ‘first commit’
git remote add origin https://github.com/your_Github_name/reop_name.git
git push -u origin master
# after the first commit 
git add . 
git commit -m  'second commit'
git push
# check the origin repository address
git remote -v 
# if you want to remove the current repository address 
git remote rm origin  	
```

#### SSH
```bash
# log into remote server using SSH
ssh -X your_user_name@IP_address    # -X: enable graphic function
# download files from server using SSH
scp your_user_name@IP_address: /file/path/on/server /file/path/on/local/computer
# upload files to server using SSH
scp /file/path/on/local/computer your_user_name@IP_address:/file/path/on/server   
# copy local ssh key to server
ssh-copy-id your_user_name@IP_address
```

#### SSHFS
Mount a remote filesystem using SFTP.
```bash
# install
sudo apt install sshfs
# mount a remote filesystem, local folder must be empty
sshfs -o follow_symlinks your_user_name@IP_address:/path/on/server /path/on/local/computer
# unmount a remote filesystem
fusermount -u /path/on/local/computer
```

#### Screen
Perform a long-running task on remote serve even if your SSH get disconnected.

```bash
# Linux screen 
sudo apt install screen
# start a session 
screen
# start a named session
screen -S session_name
# list all sessions 
screen -ls    
# enter session: id
screen -r id
# detach from the screen session 
Ctrl+a d
```

#### Filewall Setup
```bash
sudo ufw status verbose
sudo ufw allow ssh
sudo ufw allow from 222.XXX.XX.XXX
sudo ufw allow from 222.XXX.XX.XXX to any port 22
sudo ufw status numbered 
sudo ufw delete
sudo ufw default allow outgoing
sudo ufw default deny outgoing
```

#### Change Permissions

```bash
To change directory permissions in Linux, use the following:
chmod +rwx filename to add permissions
chmod -rwx directoryname to remove permissions
chmod +x filename to allow executable permissions
chmod -wx filename to take out write and executable permissions
```

#### Add Users

```bash
sudo adduser username
sudo mkdir /data/username
sudo chown -R username:username folder
```



## Python

#### Python Profiling
Profile CPU time
```bash
pip install snakeviz
python -m cProfile -o temp.dat <PROGRAM>.py
snakeviz temp.dat
```
Profile memory 

```python
import numpy as np
from memory_profiler import profile
# put a decorator here
@profile(precision=4, stream=open("memory_profiler.log","w"))
def my_fun():   
    a = np.ones(1000)
    b = np.ones(1000)
	c = np.sum(a + b)
	print(c)

if __name__ == '__main__':
    my_fun()
```
Install 

``` bash
python setup.py instal
```


## MATLAB

Install 
``` bash
sudo mount -o loop R2021a_Linux.iso /mnt
cd /mnt
sudo ./install
umount /mnt/
# License file can be found on the USTC website
```
Useful Commands
``` matlab
% Save ascii file
a = 1
filename = sprintf(‘data_%d.dat', a);
save(filename,'variable','-ascii');

% Save files with different names
for i = 1 : 10
		k = i * ones(10,10);
		filename = strcat('File', num2str(i));
		save( [filename, '.dat'],  'k', '-ascii');
end

% Read binary file
M = 101;
N = 201;
fid = fopen('file.bin', 'rb');
[data, count] = fread(fid, [M,N],'float');
fclose(fid);

% Add path
path = '/home/haipeng/MyCode/'
addpath(genpath(path),'-begin');

% Read data in a quick manner
data = dlmread(filename);

% Set two-line title 
title({'You can do it','with a cell array'})

```


## C & Fortran

C call Fortran
``` bash
# Step1:  Write the Fortran code
# Step2:  Write the C code 
#
# Suppose in the Fortran code, there is a function: 
#      myadd( n, a, b, c) 
# which performs c[n] = a[n] + b[n]
#
# In the c code, we need to call: 
#      __modulename_MOD_myadd( &n, &a, &b, &c);
#
# Also Use *nm fortran_module_name.o* to confirm the name.
#
# Step 3: Compile

gfortran -c Fortran_code.f90
gcc      -c C_code.c
gcc      -o c_call_fortran C_code.o Fortran_code.o -lgfortran  #lgfortran 调用库函数
./c_call_fortran
```

Fortran call C
``` bash
# Fortran main program named as f-call-c.f, in free format.

program f_call_c
integer :: i=1, ierr
double precision :: x=3.14159
print *, "Fortran calling C, passing"
print *, "i=",i,"x=",x
ierr = cfun(i,x)
end program f_call_c

# C function (cfun.c): note the trailing underscore in the function name cfun_

#include <stdio.h>
int cfun_(int *ip, double *xp)
{
int i = *ip;
double x = *xp;
printf("This is in C function...\n");
printf("i = %d, x = %g\n", i, x);
return 0;
}

# Compile: using Intel compilers icc and ifort
ifort -free -c f-call-c.f
icc -c cfun.c
ifort -o f-call-c-icc f-call-c.o cfun.o
./f-call-c-icc

#Compile: using gcc and gfortran
gfortran -ffree-form -c f-call-c.f
gcc -c cfun.c
gfortran -o f-call-c-gcc f-call-c.o cfun.o
./f-call-c-gcc
```

Useful Fortran Commands
``` bash
# Compile many subroutines in Fortran
# Option 1: 
use include ‘subroutine_name.f90’

# Option 2:
compile all subroutine to generate all *.o files 
gfortran *.o file -o out.o

# Fortran debug
gfortran -g -fcheck=all -Wall example.f90

# Something danger in Fortran
Fortran can not use 6 as file pointer
```

## OpenMP
Complie
``` bash
gcc -fopenmp
icpc -openmp
```

## GMT

* https://blog.seisman.info/global-relief-models/ 有介绍如何下载地形数据
* 如果要使用高精度的地形数据，一般在http://srtm.csi.cgiar.org/srtmdata/ 下载（需要能连上Google），但是对于比较大的区域，需要将多个地形数据合并在一起才能使用。首先要安装工具包gdal（Ubuntu 16.04 LTS）

``` bash
sudo add-apt-repository -y ppa:ubuntugis/ubuntugis-unstable
sudo apt update 
sudo apt install gdal-bin python-gdal python3-gdal
# (https://github.com/adamrehn/mergetiff）
```
* 安装成功后使用以下命令把多个地形数据合并成一个
	gdal_merge.py -init 255 -o out.tif srtm_56_07.tif srtm_57_07.tif
* 使用以下的命令将 .tif文件转化为能用于GMT画图的 .grd文件
	gdal_translate -of GMT out.tif srtmc_out.grd
* 在画断层或者其他构造线时，拿到的数据往往都是 .kml或者 . kmz格式的文件，这些格式的文件可以用Google Earth或者其他地图软件打开，但不能在GMT中使用，使用下面的命令转化为GMT可以使用的格式
	gmt kml2gmt CN-Faults.kml -V > CN-Faults.dat
	对于. kmz格式文件，可以先使用Google Earth或其他地图软件转为 .kml的文件，再使用以上命令。
* 如果grd文件的网格太大，可以用下面的命令来插值，获取更小网格的grd文件，-I1s表示1秒，也可以用-I1m，代表1度。
	gmt grdsample Suqian.grd -I1s -GSuqian_new_0.1.grd
* 可以使用如下命令，cut一部分grd文件
	gmt grdcut $topoFile -R范围 -GSuqian_0.5.grd
* 画不规则的图，目前想到的方法是生成该地区的grd文件，再生成对应的bln文件，在Surfer里面用assign no data功能把不想要的地方切除，注意如果网格太大，切除的效果不好，要注意grd网格和bln的尺度要相匹配，否则会有矩形边齿。 


## Linux Installation

#### Common Kits
```bash 
sudo apt-get install build-essential   # including: libc6, libc, gcc, g++, make, dpkg
sudo apt install gfortran 
sudo apt install vim
sudo apt install git
```

#### OpenMPI
```bash 
# Download the latest OpenMPI package, 
# or download the specific version from: http://www.open-mpi.org/software/ompi
wget https://download.open-mpi.org/release/open-mpi/v4.1/openmpi-4.1.1.tar.gz 
tar xvfz openmpi-4.1.1.tar.gz
cd openmpi-4.1.1
# Configure & install OpenMPI (this would take quite a while)
./configure --prefix=/usr/local/openmpi CC=gcc FC=gfortran
make
sudo make install
# Add env path at your ~/.bashrc
echo export PATH=/usr/local/openmpi/bin:$PATH >> ~/.bashrc
source ~/.bashrc
# Check
which mpirun
```

#### Anaconda
```bash 
# Install
bash Anaconda3-2019.10-Linux-x86_64.sh
enter: yes  
source ~/.bashrc

# Creat new environment
conda install -c anaconda anaconda-navigator 
anaconda-navigator
conda create --name my_env python=3.7    (install the GUI)
conda install -c conda-forge obspy
conda activate my_env

# Uninstall
conda install anaconda-clean
anaconda-clean
```

#### Cuda
```bash
# Also refer to: https://blog.nickwhyy.top/cuda/

wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-ubuntu1604.pin
sudo mv cuda-ubuntu1604.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda-repo-ubuntu1604-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-1-local-10.1.243-418.87.00/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```

## SPECFEM2D/3D

MPI Version
```bash
# 配置好gcc，gfortran和openmpi后可以安装specfem2D/3D
# 注意：openmpi编译的时候使用的CC和FC必须和安装时使用的一样
# 安装必要的包：
sudo apt-get install zlib1g-dev

# 配置， 最好给出MPIFC和MPI_INC的绝对路径
/configure FC=gfortran CC=gcc MPIFC=/usr/local/openmpi/bin/mpif90 MPI_INC=/usr/local/openmpi/include --with-mpi   
make 
```
GPU Version
```bash
./configure --with-cuda=cuda9 CUDA_LIB=/usr/local/cuda/lib64 CUDA_INC=/usr/local/cuda/include MPI_INC=/opt/mpich3.3/include --with-mpi
make

# 这里不知道CUDA_FLAGS 填什么,省略CUDA_FLAGS也可以make成功, 我是cuda10.1， 但是makefile里面最高有cuda9.0, 这里用cuda=cuda9也可以make成功
```

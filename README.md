# RAGE-on-SSD
RAGE-on-SSD is an ubuntu image with all the RAGE workflow and data pre-installed. RAGE-on-SSD image works well with SSD drives. Although it may work with flash drives but the user may find operating system running much slower compared to SSD.

## Creating RAGE-on-SSD with exisiting image
You need to have few stuffs to create the RAGE-on-SSD
-  SSD with atleast 250 GB storage
-  [balenaEtcher](https://etcher.balena.io) for creating the bootable image
-  [RAGE image]()

After downloading the RAGE image, launch balenaEtcher to flash the image onto your SSD. The process duration varies with your system's configuration but should complete in a few minutes. Upon completion, the SSD is ready for booting. 
The default username is "rabv_1" with the password "rabv@123".

**NOTE**: You may have higher storage capacity SSD, but this image is set to have 166GB, and once after creating bootable SSD, your SSD will turn into 166GB even if you have more storege space on your SSD.  If you want to utilize the
entire space of SSD, it is recommended to follow creating custom image.

# Creating a custom image

## Requirments
Following are the necessary software required to create an ubuntu image
1. [Ubnutu bootable ISO image can be dowloaded from](/https://ubuntu.com/download/desktop)
2. [Oracle VirtualBox](https://www.virtualbox.org)

## Creating VMBox Ubuntu image
Install the VirtualBox and follow the below link to install ubuntu on VMBox
https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview

## Installing Artic_nf workflow
After successful installation of ubuntu on Virtual Box, it is now the time to install all the RAGE related software/packages.
You can install all the necessary tools/packages step-by-step.

### Download and install the Miniconda
[Downlaod the Miniconda](https://docs.anaconda.com/free/miniconda/index.html)
Example:- let’s assume you have downloaded a Miniconda file named "Miniconda3-latest-Linux-x86_64.sh" and it is located in your "Downloads" folder/directory.

You can locate to your download directory using the terminal
```shell
cd /home/<user_name>/Downloads/
```
<user_name> is the name of your main directory. You can install the Miniconda as mentioned below.

```shell
bash Miniconda3-latest-Linux-x86_64.sh
```
During the installation. Proceed with "Yes" and run the conda init as mentioned by the conda installation process. 

Once the Conda is installed you can check it by running. On success installation "(base)" will appear on your left side of your writing window in the terminal. 
```shell
bash
```

It is recommended to add the following channels to Conda. This will help in fetching the software/tools/packages. 
```shell
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --set channel_priority strict
```

## Creating a directories
There are few directories which needs to be created to store the data and third-party tools. 
```shell
mkdir /home/<user>/workshop_dir
mkdir /home/<user>/workshop_dir/data
mkdir /home<user>/workshop_dir/backup
mkdir /home/<user>/workshop_dir/tools
```
**data**: Stores all the raw data
**backup**: Stores all the workflows
**tools**: Stores all the third-party tools such as dorado, seaview and others




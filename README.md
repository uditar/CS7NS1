## Setting up AWS on RH
a. Creating an instance
-	Open RH and create a linux instance -> in this case search for Ubuntu 18.04 image from images and click on launch
-	It will prompt you to select spot instance type and other settings, leave them as is
-	Once created the image appears in the top under “Sessions”
-	Right click on the image and click check connectivity info
-	Download the private keys .pem and .ppk and rename them to something memorable and easier
-	Download WinSCP and putty (for windows os)
 
 
b. Setting up WinSCP and putty
- Open WinSCP and log in by entering the host name, port number and ppk downloaded from step 5 above.

![](https://github.com/uditar/CS7NS1/blob/master/images/tempsnip.png)

![](https://github.com/uditar/CS7NS1/blob/master/images/tempsnip2.png)

-	Once this is done clone the John the Ripper git repo into the home directory i.e. ubuntu/home/code/JohnTheRipper
-	Open Putty.exe (in my case I could not open it directly from my WinSCP for some reason). Connect to putty by entering the port number,   name and keys as follows
![](https://github.com/uditar/CS7NS1/blob/master/images/tempsnip3.png)

- Open putty and login as : ubuntu

## Setting up P100 GPUs on Google cloud console
a. Creating a VM instance
- Create a new project ex.[inferno](https://console.cloud.google.com/compute/instancesAdd?project=inferno-221222)
- Create a new VM instance with the following specifications

![](https://github.com/uditar/CS7NS1/blob/master/images/customise.png)
-	Choose europe-west1 (Belgium) as google cloud only allows GPUs in some regions as listed [here.](https://cloud.google.com/blog/products/gcp/expanding-our-gpu-portfolio-with-nvidia-tesla-v100)

-	Customise the machine type as below and SSH into VM
![](https://github.com/uditar/CS7NS1/blob/master/images/customise2.png)

### Installing drivers for Tesla P100
```
sudo apt update
sudo apt upgrade
sudo apt install build-essential linux-image-extra-virtual
```
```
wget http://uk.download.nvidia.com/tesla/396.44/NVIDIA-Linux-x86_64-396.44.run.run
sudo /bin/bash NVIDIA-Linux-x86_64-396.44.run.run
```


 
 

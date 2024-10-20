# Fine-grained-classification-test-dataset-of-automatic-driving-system

We aim to create a high-coverage dataset that provides more targeted selection criteria for future researchers by finely partitioning driving scenarios. 

The fine-grained division includes but is not limited to road structures such as turning roads, ramps, lakes, intersections, roundabouts, etc. In the future, we will combine road structures with adverse weather conditions, not only focusing on ideal road conditions but also paying special attention to driving scenarios that are prone to danger, such as slippery slopes and lakes. 

In this way, we aim to provide more comprehensive data to support the safety test of the auto-drive system in different driving situations. We also offer data on the problem exposure of the monitoring system, which can visually show the status of the auto-drive system when the problem is exposed.

## Table of Contents

1.[Introduction](#introduction)  
2.[Data Download](#data-download)  
3.[Citation](#citation)  

## Introduction

The dataset includes: car driving data that changes over time, actor data (including sensor data), records of various problem exposures, and log files that can be used for playback. All data in the driving scenario is saved in a timestamp folder. Driving scenes are classified according to road structure. And a map will store all types of road structures that exist. In addition, a map file also includes a starting point that records all driving scenes on the map.The overall framework is shown in the figure.

### Driving scene display
Some example videos are shown below:

### Straight Road

### Common Road

### Ramp

### Tunnel

## Data-download

### Installation of Bridge

#### Prerequisites

* docker
```
sudo apt-get install docker.io
```
* NVIDIA Container Toolkit
```
curl https://get.docker.com | sh \
&& sudo systemctl --now enable docker
```
```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
    && curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
    && curl -s -L https://nvidia.github.io/libnvidia-container/$distribution/libnvidia-container.list | \
          sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
          sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```
```
sudo apt-get update
```
```
sudo apt-get install -y nvidia-docker2
```
```
sudo systemctl restart docker
```
 * docker-compose
 ```
     sudo curl -L "https://github.com/docker/compose/releases/download/v2.0.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
* Change File Permission
```
sudo chmod +x /usr/local/bin/docker-compose
```

#### Build And Run Apollo
* Clone apollo v8.0.0
```
# Using SSH
git clone -b v8.0.0 git@github.com:ApolloAuto/apollo.git

#Using HTTPS
git clone -b v8.0.0 https://github.com/ApolloAuto/apollo.git
```
* Build Apollo
```
cd apollo
echo "export APOLLO_ROOT_DIR=$(pwd)" >> ~/.bashrc  && source ~/.bashrc
```
run:
```
sudo rm -rf /apollo/.cache
bash docker/scripts/dev_start.sh
```
Upon successful execution, you will see the following message
```
[ OK ] Congratulations! You have successfully finished setting up Apollo Dev Environment.
[ OK ] To login into the newly created apollo_dev_lei container, please run the following command:
[ OK ]   bash docker/scripts/dev_into.sh
[ OK ] Enjoy!
```
Above If you occured error as "ERROR: Config value 'cuda' is not defined in any .rc file",you can try
```
./apollo.sh config -n
```
Run this command to enter the container
```
bash docker/scripts/dev_into.sh
```
Make the GPU version:
```
./apollo.sh build_gpu
```
After successful compilation, the following will be printed:
```
==============================================
[ OK ] Done building apollo. Enjoy!
==============================================
```
Run this command in the container to start Dreamview
```
./scripts/bootstrap.sh
```
Finally, open the link in your browser
```
http://localhost:8888/
```






## Citation

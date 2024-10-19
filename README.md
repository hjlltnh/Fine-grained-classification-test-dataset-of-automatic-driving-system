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

docker
```
sudo apt-get install docker.io
```


## Citation

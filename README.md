
# PkView 

Documentation for PkView, a Viewer for 3D and 4D functional data and Pharmacokinetic modelling. Not publicly available (yet). 

(build 0.31)
![Image 1](screenshots/Selection_177.jpg)



## Disclaimer and acknowledgments

Please acknowledge this software in any publication or other work that uses analysis, results or figures generated by this software and cite the related publiction. The new related publication is: **Irving et al (2017) maskSLIC: Regional Superpixel Generation with Application to Local Pathology Characterisation in Medical Images. [https://arxiv.org/abs/1606.09518v2](https://arxiv.org/abs/1606.09518v2)**. This publication highlights the PK modelling and latest clustering methods used in PKView. 

**This software has been developed for research purposes only, and should not be 
used as a diagnostic tool. The authors or distributors will not be responsible for 
any direct, indirect, special, incidental, or consequential damages arising of the use of this software.The current intention of this software is for "in house" use only and shouldn't be distributed without the explicit consent of the authors.**


## Installation

Executables are available for Ubuntu, Windows and macOS. 

### Windows
- unzip the pkviewer2-0.31-win64.zip package
- There are a larger number of files but find and click on the pkviewer2.exe file
- A shortcut can be created to this file on your desktop but the exe file must remain with all the other dependencies. 

### macOS
For OSx one dependency is not yet ready for high definition screens which leads to poorer resolution. 

### Ubuntu
The software can be installed from the .deb package



### Requirements

Multiple large volumes are often used or created during analysis. Therefore, a computer with enough memory is required (at least 8GB). 

## Basic Usage

#### Nifti 

This software package works with nifti volumes. Please convert dicoms to nifti first using one of a number of tools including: [itk-snap](http://www.itksnap.org/pmwiki/pmwiki.php), [dcm2nii](https://www.nitrc.org/plugins/mwiki/index.php/dcm2nii:MainPage) or the batch version which allows a number of volumes to be converted [dcm2niibatch](https://github.com/rordenlab/dcm2niix)

#### Load 4D volume

PKView loads images, rois and overlays from nifti files. 

Either: 

1) Drag and drop a 4D nifti file onto the viewer

or

2) File -> Load Image

![Image 1](screenshots/1.png)

When dragging and dropping, a window will pop up to specify whether the image is a 4D volume, ROI or overlay. 

![Image 2](screenshots/2.jpg)

The image will appear in the 3 views. 
Options
- Zoom using the **right mouse button**
- **Left mouse button** click a point
- **scroll** using the mouse wheel
- Options allow scaling based on the voxel size

![Image 1](screenshots/3.png)

#### Load ROI and overlays

Drag-and-drop or load overlays in a similar way.

For overlays specify the overlay type or a generic type (as show below)

![Image 1](screenshots/4.jpg)

Switch between loaded or generated overlays from the *current overlays* section of the **Volumes** widget. 

![Image 1](screenshots/5.png)


## General interaction

- Scroll mouse button to navigate through the volume
- Left click on a point to navigate through the volume
- Hold right button and move mouse to zoom
- Use the sliders at the bottom to navigate through the volume
- Double click on a window to expand (see below)

*Hold right button and move mouse to zoom*
![Image 1](screenshots/Screenshot_4.png)


*Double click to expand one window*
![Image 1](screenshots/Selection_204.jpg)

## Volume, ROI and overlay interaction

![Image 1](screenshots/navigation.png)


## Voxel analysis widget

- The voxel analysis widget gives the enhancement curve of the currently selected location. 

![Image 1](screenshots/6.png)

- Multiple points can be selected with multiple colors
- Mean curves for each color can be calculated
- Points can be cleared with X
![Image 1](screenshots/7.png)



## Saving images

#### Save a screen shot or plot
- Right click on an image or plot
- Click *Export*
- A view box will appear with the various format options. 
- *svg* format will allow editing of the layers and nodes in inkscape or another vector graphics viewer. 

![Image 1](screenshots/17.jpg)


#### Save an overlay to nifti

File -> Save Current overlay

## Overlay statistics widget

- Statistics for each defined ROI
- Mean, Median, Variance, Min and Max

![Image 1](screenshots/Selection_177.jpg)


## Curve clustering widget

- PCA based curve clustering allows clustering of tumour subregions based on contrast enhancement characteristics. 
- Number of clusters
- PCA modes used for clustering
- Advanced options: Merge clusters, auto merge clusters, get cluster sizes

![Image 1](screenshots/10.png)


## Overlay clustering widget

- Cluster based on a particular ROI map
- Step 1: Select the overlay of interest

![Image 1](screenshots/13.png)

- Step 2: Cluster based on the selected ROI. 
- Get slice and volume statistics

![Image 1](screenshots/12.png)

## Supervoxel widget
Create supervoxel regions within an ROI (see https://arxiv.org/abs/1606.09518v2)

![Image 1](screenshots/Selection_166.jpg)


## Mean value widget
Generate mean values from the current overlays for each ROI. 

*Example showing mean Ktrans value of each supervoxel*

![Image 1](screenshots/Selection_167.jpg)

## T1 mapping widget
Generate T1 maps from variable flip angle images (used as a preprocessing step for PK modelling)

*Using a single 4D volume with multiple flip angles*
![Image 1](screenshots/Selection_181.jpg)

*Loading muliple flip angle volumes*
![Image 1](screenshots/Screenshot_3.png)


## PK modelling widget

- Load DCE-MRI, ROI and T10 map
- Select pharamacokinetic model
- Input image parameters
- Run modelling inside the ROI

*Start of modelling*
![Image 1](screenshots/Screenshot_2.png)

*Modelling complete with newly generated Ktrans map*
![Image 1](screenshots/Screenshot_1.png)

*Still required:*
- Inclusion of Contrast-to-noise ratio restriction

## Visualisation of model fit widget
- *Additional Widgets -> PharmCurveView*
- If Pk modelling has been run or *model curves* are loaded from a nifti file then visualise the difference in parameters between the model fit and the true data. 

![Image 1](screenshots/14.png)
 


Images copyright 2016, 2017 Benjamin Irving


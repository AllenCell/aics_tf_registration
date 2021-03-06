# aics_tf_registration

[![Build Status](https://github.com/AllenCell/aics_tf_registration/workflows/Build%20Master/badge.svg)](https://github.com/AllenCell/aics_tf_registration/actions)
[![Documentation](https://github.com/AllenCell/aics_tf_registration/workflows/Documentation/badge.svg)](https://AllenCell.github.io/aics_tf_registration)
[![Code Coverage](https://codecov.io/gh/AllenCell/aics_tf_registration/branch/master/graph/badge.svg)](https://codecov.io/gh/AllenCell/aics_tf_registration)

Rigid registration algorithm for generating training/testing data for transfer function model

---

## Features
* Rigid registration of `.tiff` confocal/fluorescent microscopy images, outputting cropped images containing their mutual field of view
* Supports the following registration scenarios
	* Images at the same or different resolutions and pixel dimensions/scales
	* Full multichannel images based on a reference channel
	* Specific channels in multichannel images based on seperate reference channel
	* Multiple pairs of images with the same registration scenario at once
* Configuration of registration settings through easy-to-read `.yaml` file
* Outputs composite of registered image for easy evaluation of results

## Quick Start
In console (after installation):
```console
run_alignment --config_path `path/to/config/file.yaml`
```

## Installation
**Stable Release:** `pip install aics_tf_registration`<br>
**Development Head:** `pip install git+https://github.com/AllenCell/aics_tf_registration.git`

## Documentation
For full package documentation please visit [AllenCell.github.io/aics_tf_registration](https://AllenCell.github.io/aics_tf_registration).

## Image Requirements for Registration
In order for the registration algorithm to produce accurate results, the images must have the following requirements:

* Images must be in `.tif` or `.tiff` format. 
* The source and target images must be in separate folders and images that are to be registered to each other must share the same filename.
* Images must be 3D or 4D
* The field of view of either the source or target image must be wholly contained within the fov of the other (or cropped to be so with the settings in the config file)
* Rotation and mirroring of images (if necessary) to have matching orientations must either be done prior to registration or within the settings of the config file if it is consistent between different image pairs 
* The resolution/voxel dimensions of the images, or at least the relative scaling differences between the source and target image, should be known to within approximately 3-4 decimal units


***Free software: Allen Institute Software License***


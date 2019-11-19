## Data

Data is collected by [KITTI](http://www.cvlibs.net/datasets/kitti/raw_data.php) project.
You need to download 2011_09_26_drive_0002 and extract it in this directory. ([synced+rectified data](https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_drive_0002/2011_09_26_drive_0002_sync.zip))
You will also need [calibration parameters](https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_calib.zip).

Paper: [link](./paper.pdf)

## Experiment

The idea was simple - take one frame from KITTI data and introduce artificial bias in rotation and translation of `velo2cam`. Then use
the process decribed in a paper to find correction in `R` and `T`.
Simulated annealing approach is used (Random Search + Suboptimal solution acceptance with diminishing probability).

## Results

I've failed to reproduce the results. It seems that my implementation of loss function is not correct. Euclidean distance between true rotation/translation and predicted ones increases as the number of iterations raises.
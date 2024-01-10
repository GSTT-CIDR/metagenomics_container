# Metagenomics service singularity/apptainer setup and execution
A guide for running CIDR metagenomics from singularity/apptainer images. The tools here can be cloned and built independent of containers from their GitHub repos, [organism_query](https://github.com/dan-ward-bio/organism_query_ and [CIDR_metagenomics (not up yet)](https://github.com/).

## Rationale
Distribution of CIDR metagenomics software across the NHS metagenomics NoE 

## Apptainer installation
Install singularity on the host machine through either:
1. OS package manager: yum/apt [Apptainer guide](https://apptainer.org/docs/admin/main/installation.html)
2. Mamba: ```mamba install apptainer```
3. From source: [Apptainer guide](https://apptainer.org/docs/admin/main/installation.html)

## Building apptainer image from definition
**If you have already received the _.sif_ image, procede to the next step _Running apptainer images_.** 
1. Clone the container definition repo: ```git clone``` 
2. Navigate to the directory containing the container definition
3. Build the 
```
git clone 
sudo apptainer build organism_query metag_v1.def


```

## Running apptainer images
2. Setting limit for container to run
```ulimit -n 20000```

3. ```apptainer run --bind /tmp/.X11-unix:/tmp/.X11-unix --bind /:/mnt --env DISPLAY=$DISPLAY organism_query.sif ```
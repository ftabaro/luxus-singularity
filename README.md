# A Singularity container for the LuxUS tool

For details about the LuxUS method see the [paper](https://www.biorxiv.org/content/10.1101/536722v2) and the [repository](https://github.com/hallav/LuxUS).

## Download a premade LuxUS image from Singularity Hub

```
$ singularity pull shub://ftabaro/luxus-singularity
```

This will download a premade image from the Singularity Hub into the current workind directory into `luxus-singularity_latest.sif`. 

## Build local image

1. Clone this repository
2. `cd` into che cloned repository
2. Build

```
$ singularity build Singularity luxus-singularity.sif
```

This will build the image in the current folder into `luxus-singularity.sif`.

## Run LuxUS

1. Prepare data

```
$ singularity run --app prepare luxus-singularity.sif [options]
```

2. Run the analysis

```
$ singularity run --app luxus luxus-singularity.sif [options]
```

# A Singularity container for the LuxUS tool

For details about the LuxUS method see the [paper](https://www.biorxiv.org/content/10.1101/536722v2) and the [repository](https://github.com/hallav/LuxUS).

## Download a premade LuxUS image from Singularity Hub

```
$ singularity pull shub://ftabaro/luxus-singularity
```

This will download a premade image from the Singularity Hub into the current working directory into `luxus-singularity_latest.sif`. 

## Build local image

1. Clone this repository
2. `cd` into che cloned repository
2. Build

```
$ singularity build Singularity luxus-singularity.sif
```

This will build the image in the current folder into `luxus-singularity.sif`.

## Run LuxUS

1. Set variables

```
INPUT_FOLDER=LuxUS/data/
OUTPUT_FOLDER=test
OUTPUT_FILE=test.txt
```

2. Prepare data

```
$ singularity run --app prepare luxus-singularity.sif \
  -i $INPUT_FOLDER/proportion_table_test_data_diff1.txt \
  -d $INPUT_FOLDER/design_matrix_test_data_diff1.txt \
  -o $OUTPUT_FOLDER \
  -r 12 \
  -t 1 \
  -u 0.1 \
  -y $OUTPUT_FOLDER/window_mean_coverage_test_data_diff1.txt \
  -z $OUTPUT_FOLDER/window_number_of_cytosines_test_data_diff1.txt
```

3. Run the analysis

```
$ singularity run --app luxus luxus-singularity.sif \
  -d input_for_luxus_1.txt \
  -o $OUTPUT_FOLDER \
  -i $INPUT_FOLDER \
  -j $OUTPUT_FILE \
  -x 1 \
  -p 1 \
  -w 1
```

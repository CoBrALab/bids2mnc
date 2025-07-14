# bids2mnc -- A MINCified BIDS Derivatives Generator

A script, relying on [libBIDS.sh](https://github.com/CoBrALab/libBIDS.sh) which
converts NIFTI images in a BIDS dataset to MINC, and inserts JSON metadata
into the header of each MINC file according to the inheritance principles in
BIDS.

MINC files are generated as a BIDS derivatives dataset, with the same directory structure and filenames as the orignal
NIFTI files.

## Dependencies

bids2mnc uses [libBIDS.sh](https://github.com/CoBrALab/libBIDS.sh) for loading and manipulating the BIDS dataset
structure, and [jq](https://jqlang.org/https://jqlang.org/) for manipulating JSON metadata inside BIDS.

Conversion is achieved with `nii2mnc`, available in [minc-tools](https://github.com/BIC-MNI/minc-tools), available as
packages in many major Linux distributions, or otherwise available in the mega package
[minc-toolkit](https://bic-mni.github.io/#v1-version-1009-legacy) and
[minc-toolkit-v2](https://bic-mni.github.io/#v2-version-1918)

## Usage

```bash
$ git clone --recursive https://github.com/CoBrALab/bids2mnc.git # Recursive needed to pull in libBIDS.sh dependency
$ cd bids2mnc
$ ./bids2mnc.sh /path/to/bids/dataset
```

## Command line options

```
$ bids2mnc.sh
A tool to generate metadata-rich MINC files from a BIDS dataset
Usage: ./bids2minc.sh [-h|--help] [-r|--row-filter <arg>] [--(no-)clobber] [--(no-)debug] [--(no-)dry-run] <bids_path>
        <bids_path>: Path to BIDS dataset
        -h, --help: Prints help
        -r, --row-filter: Filter BIDS files for conversion using regex on row content format <column_name>:<regex_pattern> (empty by default)
        --clobber, --no-clobber: Overwrite existing files (off by default)
        --debug, --no-debug: Debug mode, print all commands to stdout (off by default)
        --dry-run, --no-dry-run: Dry run, don't run any commands, implies debug (off by default)
```

# bids2mnc

A script, relying on [libBIDS.sh](https://github.com/CoBrALab/libBIDS.sh) which
converts all NIFTI images in a BIDS dataset to MINC, and inserts JSON metadata
into the header of each MINC file according to the inheritance principles in
BIDS.

## Usage

```bash
$ git clone --recursive https://github.com/CoBrALab/bids2mnc.git # Recursive needed to pull in libBIDS.sh dependency
$ cd bids2mnc
$ ./bids2mnc.sh /path/to/bids/dataset
```

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

## Help

```
A tool to generate metadata-rich MINC files from a BIDS dataset
Usage: ./bids2minc.sh [-h|--help] [-r|--row-filter <arg>] [--(no-)clobber] [--(no-)debug] [--(no-)dry-run] <bids_path>
        <bids_path>: Path to BIDS dataset
        -h, --help: Prints help
        -r, --row-filter: Filter BIDS files for conversion using regex on row content format <column_name>:<regex_pattern> (empty by default)
        --clobber, --no-clobber: Overwrite existing files (off by default)
        --debug, --no-debug: Debug mode, print all commands to stdout (off by default)
        --dry-run, --no-dry-run: Dry run, don't run any commands, implies debug (off by default)
```

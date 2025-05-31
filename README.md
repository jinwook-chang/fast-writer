# fast-writer

`fast-writer` is a command-line interface (CLI) tool built on the Polars library, designed for fast and efficient processing of various file formats (CSV, TSV, Excel, Parquet). It offers features like file preview, format conversion, and merging multiple files.

## Key Features

*   **File Preview**: Quickly view the first (`head`) or last (`tail`) few lines of a file.
*   **File Format Conversion**: Supports mutual conversion between CSV, TSV, Excel (.xlsx), and Parquet files.
*   **File Merging**: Merges multiple files row-wise. You can specify particular files or merge all files within a folder.

## Installation

```
pip install fast-writer
```

```bash
git clone https://github.com/jinwook-chang/fast-writer
cd fast-writer
pip install .
```

## Usage


```bash
fast-writer --help
```

### File Preview
```bash
# View the first 5 lines of example.csv
fast-writer head output/iris.csv

# View the last 10 lines of data.parquet
fast-writer tail head output/iris.csv -n 10
```

### File Format Conversion
```bash
# Convert input.csv to output.parquet
fast-writer convert output/iris.csv parquet -o output/iris.parquet

# Convert data.xlsx to data.csv (output filename is automatically assigned)
fast-writer convert output/iris.csv tsv

```

### File Merging
```bash
# Merge file1.csv and file2.csv into merged.csv
fast-writer merge files output/iris.csv output/iris2.csv -o output/merged.csv

# Merge all .csv files in a folder into all_data.parquet
fast-writer merge folder ./output --pattern "*.csv" -o output/all_data.parquet
```

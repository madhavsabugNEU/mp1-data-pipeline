# MP1 Data Pipeline

This project is a command line data pipeline that loads, validates, cleans, and saves the data using settings from a YAML configuration file. Data moves through the pipeline in five stages: the input and configuration files are checked and loaded, the data is validated, it is cleaned by removing duplicates, missing values, and outliers, and the result is saved as a CSV along with a printed cleaning report. "pipeline.py" coordinates these stages, while the logic is in the "src/" package. "data_loaders.py" loads CSV, JSON, and YAML files based on their extension, and "data_validator.py" checks that their columns exist and removes rows with invalid numeric values. "data_processor.py" applies the cleaning steps and creates the cleaning report, "data_output.py" saves the cleaned data and creates the output folder if needed, and "utils.py" handles logging setup and file validation. 

## Usage

```bash
python pipeline.py --input fixtures/sample_data.csv --output output/clean.csv --config config/config.yaml --verbose
```

## Example Output

```text
Cleaning report:
{'rows_before': 98, 'rows_after': 92, 'rows_removed': 6, 'columns_before': 5, 'columns_after': 5, 'columns_removed': 0}
```
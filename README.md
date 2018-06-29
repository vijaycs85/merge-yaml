[![Build Status](https://travis-ci.com/EdisonLabs/merge-yaml.svg?branch=1.x)](https://travis-ci.com/EdisonLabs/merge-yaml)

# merge-yaml

## Overview
Provides a composer plugin which merges yaml files.

## Installation

Configure the plugin in your composer.json file using for example:
```
"extra": {
    "merge-yaml": {
        "files": [
            "database.sanitize"
        ],
        "locations": [
            "app/modules",
            "app/profiles",
        ],
        "output-dir": "NOT-PUBLIC-FOLDER"
    }
}
```
Where:
- `files`: List of filenames (without the yml extension) to scan for.
- `locations`: List of paths to scan for yaml files.
- `output-dir`: The directory where the merged files will be placed.

## How does it work
Every time that you run `composer install` or `composer update`, the plugin will scan the locations and merge the yml files to the output directory.

### Command
You can also use the command `composer merge-yaml` to run the merge process.

Use the option `--config` to specify a config.json file to override the config defined in the `composer.json`: `composer merge-yaml --config=config.json`.


## Automated Tests and Code Sniffer
This repository is integrated with [Travis CI](https://travis-ci.com/EdisonLabs/merge-yaml) to perform tests and detect PHP standards violations.

# README


## 1 Setup

### 1.1 Set up the repo for the Jupyter Notebook

Clone this repository.

Start by cloning the repo, to create a local copy of this folder in your machine.

In the terminal:

```
cd ~/Documents/

git clone https://github.com/audantic/take-home-project-data-analyst.git

cd take-home-project-data-analyst
```

### 1.2 Set up Docker

Install Docker: https://www.docker.com/community-edition#/download


This may take a while depending on download speeds.

```
docker pull jupyter/scipy-notebook
```

### 1.3 Start the notebook

```
docker run -it --rm -p 8888:8888 -v $(pwd):/home/jovyan/work jupyter/scipy-notebook
```

In the terminal, it will say something like:

```bash
$ docker run -it --rm -p 8888:8888 -v $(pwd):/home/jovyan/work jupyter/scipy-notebook
/usr/local/bin/start-notebook.sh: ignoring /usr/local/bin/start-notebook.d/*

Container must be run with group root to update passwd file
Executing the command: jupyter notebook
[I 20:38:18.195 NotebookApp] The Jupyter Notebook is running at:
[I 20:38:18.195 NotebookApp] http://[all ip addresses on your system]:8888/?token=c08dd7b6e98ac6658203af4426626e1ae2514cdb8c60c864
[I 20:38:18.195 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 20:38:18.196 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://localhost:8888/?token=c08dd7b6e98ac6658203af4426626e1ae2514cdb8c60c864
```

Copy/paste this URL into your browser.

Once the notebook is running, go into the work directory and open the "project.ipynb"



## 2 Dataset

The dataset is a portion of what we use for building predictive models.

Columns:

Overview
Each row represents a home sale.

We try to predict both home sales, and types of sales.

When audantic_target=1, this is the type of transaction we are trying to predict.


Group                  | Column                     | Description
---------------------- | --------                   | ------------
Response Variable      | `audantic_target`          | 1 or 0, if we are trying to predict
ID                     | `pid`                      | property unique id
ID                     | `did`                      | sales document unique id
ID                     | `sfr`                      | bool for is single family home
Geographic             | `fips`                     | county id
Geographic             | `zipcode`                  | zipcode
Property               | `square_footage`           |
Property               | `year_built`               |
Property               | `equity`                   |
Property               | `estimated_value`          |
Property               | `tax_assessed_value`       |
Property               | `length_of_ownership`      |
Demographic            | `est_household_income_val` | estimated income
Demographic            | `mosaic_hh_val`            | demographic variable for home
Demographic            | `mosaic_zip4_val`          | demographic variable for neighborhood
Demographic            | `mosaic_diff`              | difference between home and neighborhood demographics
Sale Descriptors       | `sale_amount`              | home sale price
Sale Descriptors       | `seller_name`              |
Sale Descriptors       | `buyer_name`               |
Sale Descriptors       | `seller_occupied`          | if seller lived in the house
Sale Descriptors       | `document_type`            | Warranty Deed, Grant Deed, etc.
Sale Descriptors       | `distress_circumstance`    |
Sale Descriptors       | `transfer_type`            |

## Objective

The objective of the take home project is to demonstrate how you approach data analysis. 

- What is your thought process? 
- What technical skills do you have? 
- Can you generate insights from the given dataset?

You can create any or all of the following:

- Summary statistics
- Segment analysis
- Build charts
- Build histograms

Suggestions for starting points:

- Is there a difference between zipcodes?
- Is there a difference by year built buckets?
- Is there a difference in the property features between audantic_target=1 and =0?

## Reference

[Data visualization with Pandas](https://pandas.pydata.org/pandas-docs/stable/visualization.html)


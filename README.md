# Rodent Abatement Predictive Analysis

This repository contains all the code and all data we may publicize related to the
[Rodent Abatement Predictive Analysis](https://osf.io/v5huw/). [Our paper](https://arxiv.org/abs/1807.03860) on this project was accepted to the Mining Urban Data Workshop at KDD2018 in London.

## Requirements

The code in this repository is written in Python. We used Python 3.6.3. The
work is done in Jupyter notebooks. If you do not have Python installed on your
machine, we recommend
[Anaconda](https://www.anaconda.com/download/?lang=en-us).  All other Python
package requirements are contained in `requirements.txt` and can be installed
with `conda install -r requirements.txt -c conda-forge` if using conda, or `pip
install -r requirements.txt` if not.

Note that if you are using Python 3.7, many of the geospatial packages haven't
yet provided binary installation packages. If you experience compilation problems,
try running the following commands:

```bash
pip install cython
pip install git+https://github.com/jswhit/pyproj.git
pip install git+https://github.com/Toblerity/Fiona.git
```

## Table of Contents

There are several computations that are performed in this repository. All of them
may be found in the `notebooks` folder.

### Data prep

We have several scripts which perform data preparation. These are the scripts which
begin with the number `1`. They should be run in order.

We note that each of these scripts requires access to specific backend DC
databases, and so you probably will not be able to run them. However, we have
included the outcomes of these scripts in the `notebooks/data` folder.

### Model selection

The script `2-model-selection.ipynb` actually performs model selection. Here
we perform temporal cross-validation on the features generated by our data
prep scripts and actually choose our best model.

### Target Selection

The script `3-generate-targets.ipynb` actually generates the targets that
we assigned to inspectors to target. Several maps of the data and targets
are also available here.

### Field Validation Evaluation

The script `4-field-validation-evaluation.ipynb` looks at the results of
our field validation. The outcomes of our field validation, along with the 
scores we compared to those outcomes, are in the `notebooks/data` folder.

## Data

For this project, we pulled data from specific DC backend databases. However, 
versions of much of the data we use are available on DC's [Open Data Portal](https://opendata.dc.gov/). 
We also provide static copies of the modeling data created by our data prep 
notebooks in the `notebooks/data` folder.

## Contributors

This code was written primarily by Peter C. Casey (peter.casey@dc.gov), with
some contributions from Kevin H. Wilson (@khwilson; kevin.wilson@dc.gov).

## License

See [LICENSE.md](https://github.com/thelabdc/DOH-RodentAbatement-public/blob/master/LICENSE.md).

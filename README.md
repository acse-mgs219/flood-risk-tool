## Flood Risk Prediction tool

In environmental hazard assessment, risk is defined as the probability of a hazardous event occuring multiplied by the consequences of that event. Thus high risk can be the result of frequent events of low consequence or rare events of high consequence; the highest risk scenarios are often not obvious.

The Environment Agency routinely collects data on rainfall, sea level and river discharge and has published flooding probability maps that indicate areas of England that fall within four flood probability bands, based on the recurrence interval of flood levels that cause property damage and threat to life. These bands are very low probability (flooding expected once per 1000 years), low probability (flooding expected once per 100 years), medium probability (flooding expected once per 50 years), and high probability (flooding expected once per 10 years).

This tool calculates flood probabilities and risks for postcodes in England.

### Installation Guide

```
language: python
```
  - python "3.7"
```
install:
```
  - pip install -r requirements.txt
  - pip install -e
  - pip install pandas
  - pip install numpy
  - pip install requests
  - pip install matplotlib
```
script: 
```
  - pip install pytest pytest-cov #install test framework
  - python -m pytest flood_tool --cov=flood_tool
  - pip install sphinx #for documentation
  - python -m sphinx docs docs/html
  - python -m score -v #also check scoring runs

### User instructions

This tool has capilities of:
  - Obtaining flood probability bands and sorted results given list of UK postcodes
  - Producing analysis of flood risk given list of UK postcodes
  - For an input list of UK postcodes, by accessing Rainfall API to get the live rainfall data of a whole day, providing flood warning alerts of high risk area.
  - Analyzing historical rainfall data across the UK of a specific date. (As an example, an analysis of Oct.6th's rainfall data is demonstrated)

### Documentation

The code includes [Sphinx](https://www.sphinx-doc.org) documentation. On systems with Sphinx installed, this can be build by running

```
python -m sphinx docs html
```

then viewing the `index.html` file in the `html` directory in your browser.

For systems with [LaTeX](https://www.latex-project.org/get/) installed, a manual pdf can be generated by running

```
python -m sphinx  -b latex docs latex
```

Then following the instructions to process the `FloodTool.tex` file in the `latex` directory in your browser.

### Testing

The tool includes several tests, which you can use to checki its operation on your system. With [[pytest](https://doc.pytest.org/en/latest) installed, these can be run with

```
python -m pytest flood_tool
``

The current version also includes a speed scoring algorithm. This can be run with.

```
python -m score
```

in the main repository directory.

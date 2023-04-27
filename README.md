# mtdecider
MT Decider Jupyter notebooks for automated MT evaluation

## Introduction
Evaluating machine translation, with increasing numbers of languages, test sets, MT services and MT system configurations, becomes hard to do manually. The Python library [mteval](https://pypi.org/project/mteval/) addresses this by automating evaluation with multiple automatic evaluation metrics like [BLEU](https://github.com/mjpost/sacrebleu) and [COMET](https://github.com/Unbabel/COMET).

This repository contains a collection of Jupyter notebooks that makes use of `mteval` to translate test data with online MT services and calculate the metrics on the machine translation output. The Jupyter notebooks can be run directly on [Google Colab](https://colab.research.google.com/) which requires a Google account or your own local Jupyter notebook environment (keep in mind that  calculating COMET requires a GPU).

When you only have a few languages to evaluate on few MT systems, you might be better served by using the evaluation tools/libraries [sacreBLEU](https://github.com/mjpost/sacrebleu) and [COMET](https://github.com/Unbabel/COMET) directly without the overhead of an automation framework around them.

## Installation
Installing [mteval](https://pypi.org/project/mteval/) in your Jupyter notebook environment is sufficient. To use the online MT services for translation, you need to add API authentication keys as described [here](https://github.com/achimr/mteval#setting-up-cloud-authentication-and-parameters-in-the-environment).

## Translation

### Test datasets
Test datasets to evaluate MT systems typically consist of at least a couple hundred to 1,000-2,000 source sentences and their human reference translations. For MT Decider these have to be stored in separate plain text files in UTF-8 encoding. The files need to contain one sentence per line and should not contain any markup. MT Decider expects the following folder structure under a `base_folder` (changeable in the Jupyter notebooks):
```
base_folder
|
+-<source language id>_<target language id>
  |
  +-<test set name>
    |
    +-src.<source language id>-<target language id>.<source language id>
      ref.<source language id>-<target language id>.<target language id>
```
You can manually add the test files for your own datasets or you can specify a dataset supported by sacreBLEU. A current list is available with `sacrebleu --list`, you need to check whether the language pair you want to evaluate is available in the dataset.

### Translation set CSV
Translation sets need to be listed in a `translation_sets.csv` file with the following format:
```
<source language id>,<target language id>,<test set name>
```
E.g. to translate the English→German WMT20 and English→Italian WMT09 test sets:
```
en,de,wmt20
en,it,wmt09
```

### Translation
Translation with generic online MT engines: `mtd_translate.ipynb` [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/achimr/mtdecider/blob/main/nbs/mtd_translate.ipynb)

## Evaluation with automatic metrics

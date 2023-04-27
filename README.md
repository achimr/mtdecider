# mtdecider
MT Decider Jupyter notebooks for automated MT evaluation

## Introduction
Evaluating machine translation, with increasing numbers of languages, test sets, MT services and MT system configurations, becomes hard to do manually. The Python library [mteval](https://pypi.org/project/mteval/) addresses this by automating evaluation with multiple automatic evaluation metrics like [BLEU](https://github.com/mjpost/sacrebleu) and [COMET](https://github.com/Unbabel/COMET).

This repository contains a collection of Jupyter notebooks that makes use of `mteval` to translate test data with online MT services and calculate the metrics on the machine translation output. The Jupyter notebooks can be run directly on [Google Colab](https://colab.research.google.com/) which requires a Google account or your own local Jupyter notebook environment (keep in mind that  calculating COMET requires a GPU).

When you only have a few languages to evaluate on few MT systems, you might be better served by using the evaluation tools/libraries [sacreBLEU](https://github.com/mjpost/sacrebleu) and [COMET](https://github.com/Unbabel/COMET) directly without the overhead of an automation framework around them.

## Installation
Installing [mteval](https://pypi.org/project/mteval/) in your Jupyter notebook environment is sufficient. To use the online MT services, you need to add API authentication keys as described [here](https://github.com/achimr/mteval#setting-up-cloud-authentication-and-parameters-in-the-environment).

## Translation

## Evaluation with automatic metrics

# Python Installation

## Installing ![Anaconda Python](https://www.continuum.io/sites/all/themes/continuum/assets/images/logos/logo-horizontal-large-white.svg)
Download and install Anaconda from the following link:
[Anaconda for MacOS](https://www.continuum.io/downloads?gclid=Cj0KEQjwg47KBRDk7LSu4LTD8eEBEiQAO4O6r3zXiie9ZczoXFp3Sz8NNlxpIX7CQqvWGHF7qGFJX2caAqXA8P8HAQ)

## Create a Python 2.7 Environment
```$ conda create -n py3 python=2.7 anaconda```

## To Activate Python 2.7 Environment
```$ source activate py2```

## To Deactivate Python 2.7 Environment
```$ source deactivate py2```

## Create a Python 3.5 environment
```$ conda create -n py3 python=3.5 anaconda```

## To Activate Python 3.5 Environment
```$ source activate py3```

## To Deactivate Python 3.5 Environment
```$ source deactivate py3```

## Update or Upgrade Python
If you are in an environment with Python version 3.4.2, this command will update Python to 3.4.3, which is the latest version in the 3.4 branch:

```$ conda update python```

And this command will upgrade Python to another branch such as 3.5 by installing that version of Python:

```$ conda install python=3.5```

## whereami

An application Uses WiFi signals and machine learning (sklearn's RandomForest) and allow user to predict their location with pinpoint accuracy.

### Installation

    pip install whereami

### Usage

```bash
# in your bedroom, takes a sample
whereami learn -l bedroom

# in your kitchen, takes a sample
whereami learn -l kitchen

# get a list of already learned locations
whereami locations

# cross-validated accuracy on historic data
whereami crossval
# 0.99319

# use in other applications, e.g. by piping the most likely answer:
whereami predict | say
# Computer Voice says: "bedroom"

# probabilities per class
whereami predict_proba
# {"bedroom": 0.99, "kitchen": 0.01}
```

If you want to delete some of the last lines, or the data in general, visit your `$USER/.whereami` folder.

### Python

Any of the functionality is available in python. Commands:

    from whereami import learn
    from whereami import get_pipeline
    from whereami import predict, predict_proba, crossval, locations

### Tests

    git clone https://github.com/aditya-muni/whereami
    cd whereami
    python setup.py install
    tox

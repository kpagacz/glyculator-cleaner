# Metronome
[![Build Status](https://travis-ci.org/kpagacz/glyculator-cleaner.svg?branch=app)](https://travis-ci.org/kpagacz/glyculator-cleaner)
[![Maintainability](https://api.codeclimate.com/v1/badges/c6147e4561478ec28b30/maintainability)](https://codeclimate.com/github/kpagacz/metronome/maintainability)
[![codecov](https://codecov.io/gh/kpagacz/metronome/branch/app/graph/badge.svg)](https://codecov.io/gh/kpagacz/metronome)


## Introduction
Metronome is a very simple python app designed to find a pattern in a series of time points. 
Given a set of differences between consecutive date and time-described time points 
and designated frequency it tries to fit the data into the pattern of time points repeating in the designated frequency.

Underneath the hood the predictions are handled by a tensorflow.keras neural network. The web engine is setup
in Flask. Metronome currently does not have a production-grade hosting engine attached to it. The server packaged
with the app is the one bundled with Flask - Werkzeug and it is not dedicated to production.

## Metronome setup
### Requirements
Metronome requires Python version 3.6+.

### Installation
Using the shell:
```bash
git clone https://github.com/kpagacz/metronome
cd metronome
pip install -r requirements.txt
```

### Running
Using the shell:
```bash
python cleaner.py
```

Once this command is ran Metronome listens on the default port 5000 for icoming HTTP calls. Default port can be modified in cleaner.py file
via port argument to app.run(port=port) call.
```python
app.run(port=8080)
```
After such a change and a restart of the app Metronome will listen on port 8080. You can set the port argument to an arbitrary value.

## Metronome API
Metronome currently exposes a single endpoint: /v1/models/metronome

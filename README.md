name: Run Python 

on: [push]

jobs:
  run-python-script:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v2

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: 3.8

    - name: Run Python Script
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt  # Add this line if you have any external dependencies
        python your_script.py

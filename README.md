# interpretable-machine-learning

# psa-analysis

The purpose of the research is to see whether interpretable machine learning models can be helpful in assessing pre-trial risk, in comparison to the Arnold foundation's current methods. Our goal will be to take their pre-trial risk measure (PSA), create our own risk assessment tools using interpretable machine learning methods, and do an empirical comparison. 

# setup

Getting this project to work is somewhat involved, because it uses a library that is only available in source form from git and there's something weird going on with the ```.dll```s.

Begin by running ```conda env create --file environment.yaml --prefix ./env``` to create the local conda environment. Activate this environment with ```conda activate ./env```, then navigate to your github folder and run ```git clone https://github.com/ustunb/risk-slim.git```. 

If on Windows and possibly on other machines (not tested there yet), you will need to edit ```setup.py```. Replace all instances of ```libraries=["m"]``` with ```libraries=["msvcrt"]```. Run ```pip install ./risk-slim```; if you get complaints about being unable to load ```m.dll```, edit ```setup.py``` as described above.

Trying to run Jupyter from PyCharm doesn't seem to work. I have not been able to get it to work. Run Jupyter from the Anaconda prompt exclusively.

If you have other troubles while running, you will need to copy all files which begin with ```libcrypto``` and ```libssl``` from ```env/Library/bin``` to ```env/DLLs```. This may not actually be necessary so give it a test yourself.

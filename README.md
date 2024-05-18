# MojoKnapsack

## Goal

Goal:

Compare Mojo and Python knapsack performance

## Local Dev

### Base Requirements

- Python >= 3.11.6
- Mojo 24.2.0
- Ubuntu 23 (Mantic Minotaur)

### Installation
##### Clone the source directly from Github:
```sh
$ git clone https://github.com/harrisafoster/ReactMojo.git
$ cd ReactMojo
```
##### Create & activate your Python virtual environment:
```sh
$ python3 -m venv .venv
$ source ./.venv/bin/activate
```
##### Install required packages with:
```sh
$ pip install -r requirements.txt
```

#### Ensure proper Python/Mojo connection
```sh
$ sudo nano ~/.bashrc
# Add these lines to your .bashrc file: 
find-python-for-mojo() {
    libpath=$(python3 -c 'import sysconfig; print(sysconfig.get_config_var("LIBDIR"))')
    pythonlib=$(ls $libpath | grep "libpython3.*[0-9]\.so$")
    export MOJO_PYTHON_LIBRARY=${libpath}/${pythonlib}
}

mojopy() {
    find-python-for-mojo
    mojo $@
}
export LLVM_SYMBOLIZER_PATH=/usr/bin/llvm-symbolizer
$ source ~/.bashrc
```


### Use
#### To run the Python version simply use these commands (with .venv activated):
```sh
$ python optimization.py
```

#### To run the Mojo version from the Modular cli simply use these commands:
```sh
$ mojopy stock_algo.🔥
```

#### To build the Linux executable version of the mojo script use these commands:
```sh
$ mkdir build
$ mojopy build stock_algo.🔥 -o build/stock_algo
$ ./build/stock_algo
```

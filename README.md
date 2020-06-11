This is a basic implementation of the afl-fuzzer

## Install afl
Use the following command
```shell
    $ sudo apt-get install afl
```
Or
    1. Clone git repository of AFL
    ```shell
        $ git clone https://github.com/google/AFL.git
    ```
    2. Change directory and run make and make install
    ```shell
        $ cd AFL
        $ make and make install
    ```

There are two folders in the repository:

## Basic-Fuzzing

This contains a simple C++ code taking two inputs a,b and finding a/b.

The program crashes for a/b not defined.

There are two folders `input` and `output`. The `input` folder contains test file `in`.
The results will be stored in the `output` folder.

Compile the code div.cpp using afl-g++ : 
```shell
    $ afl-g++ -o div div.cpp
```
Start fuzzing the code using the following commands :
```shell
    $ afl-fuzz -i input/ -o output/ ./div -nr input/in
```
## Test-tcpdump

We try to fuzz a software tcpdump which is a data-network packet analyzer.

The folder contains the source code of tcpdump.


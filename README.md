Setting up environment:

* Create Conda environment:
    conda create -n nrf python=3.10
    conda activate nrf
    pip install west

* Install Cmake:
    conda install cmake ninja

Klona nRF SDK med west
    mkdir "$env:USERPROFILE\ncs"
    cd "$env:USERPROFILE\ncs"
    west init -m https://github.com/nrfconnect/sdk-nrf
    west update
    west zephyr-export
    pip install -r zephyr/scripts/requirements.txt
    pip install -r nrf/scripts/requirements.txt
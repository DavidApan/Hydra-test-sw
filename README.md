Setting up environment:

* Create Conda environment:
```
    conda create -n nrf python=3.10
    conda activate nrf
    pip install west
```

* Install Cmake:
```
    conda install cmake ninja
```

* Klona nRF SDK med west

```
    mkdir "$env:USERPROFILE\ncs"
    cd "$env:USERPROFILE\ncs"
    west init -m https://github.com/nrfconnect/sdk-nrf
    west update
    west zephyr-export
    pip install -r zephyr/scripts/requirements.txt
    pip install -r nrf/scripts/requirements.txt
```

* Sätt miljövariabler
```
$env:ZEPHYR_TOOLCHAIN_VARIANT = "gnuarmemb"
$env:GNUARMEMB_TOOLCHAIN_PATH = "C:\Program Files (x86)\GNU Arm Embedded Toolchain\10 2021.10"
$env:BOARD_ROOT = "C:\Users\david.levy\ncs\cwatch"
```

* bygg
```
west build -b nrf52840_cwatch_board .

```

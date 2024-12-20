# generic_receiver 塩田修正版

## Description

`generic_receiver` is an RX demo application that demonstrates receiving _generic_ data using Rivermax API of the [Rivermax SDK](https://developer.nvidia.com/networking/rivermax).

>The code is provided "As Is" and any express or implied warranties, including,
but not limited to, the implied warranties of merchantability and fitness for a particular
purpose are disclaimed.

### Details

* Release date: 14-Aug-2024
* Update date: 14-Aug-2024
* Version: 1.51.6

### Tested on

* Rivermax: 1.51.6
* OFED: 24.07-0.6.1.0
* WinOF2: 24.7.50000
* OS: 
  * Ubuntu 22.04
  * Windows 10
* CUDA: 12.5
* Hardware:
  * ConnectX-6 DX
  * BlueField-2

## How to Build

From the `generic_receiver` directory run the following commands:

```shell
$ cmake -B ./build
$ cmake --build ./build
```

The resulting binary can be found in directory `build`.

The application can be used to demonstrate GPUDirect. Use the following command line to build with [CUDA-Toolkit](https://docs.nvidia.com/cuda/) support:

```shell
$ cmake -DRIVERMAX_ENABLE_CUDA=ON -DCMAKE_CUDA_COMPILER:PATH=/usr/local/cuda/bin/nvcc -B ./build
$ cmake --build ./build
```

## How to Run / Examples

### Synopsis & Examples

```shell
sudo ./build/generic_receiver --interface-ip <local IP> --streams 64 --cpu-affinity 24,25 --gpu 0                       (1ポートから64ストリームを受信)
sudo ./build/generic_receiver --interface-ip <local IP1>,<local IP2> --streams 128 --cpu-affinity 24,25,26,27 --gpu 0   (2ポートから64ストリームずつ受信)
```

## Known Issues / Limitations

None identified so far 

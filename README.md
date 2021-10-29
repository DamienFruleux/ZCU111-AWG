# ZCU111 - Arbitrary Waveform Generator

## Summary

[Introduction](https://github.com/DamienFruleux/ZCU111-AWG/#introduction)

[ZCU111 caracteristics](https://github.com/DamienFruleux/ZCU111-AWG/#ZCU111-caracteristics)

[Project Description](https://github.com/DamienFruleux/ZCU111-AWG/#Project-Description)



# Introduction

This project provides an example design for working with the [Zynq UltraScale+ RFSoC RF Data Converter](https://www.xilinx.com/products/intellectual-property/rf-data-converter.html) on the [Zynq UltraScale+ RFSoC ZCU111 Evaluation Kit](https://www.xilinx.com/products/boards-and-kits/zcu111.html). 

You can read the [Zynq UltraScale+ RFSoC RF Data Converter v2.6 Gen 1/2/3 Product Guide (PG269)](https://www.xilinx.com/content/dam/xilinx/support/documentation/ip_documentation/usp_rf_data_converter/v2_6/pg269-rf-data-converter.pdf) for more details on the IP core.

Specifically, we will use the ZCU111 as an [Arbitrary Waveform Generator](https://en.wikipedia.org/wiki/Arbitrary_waveform_generator) (AWG). In this way, we will be able to generate any arbitrarily defined waveshape.

The big advantage of using a solution like this is the flexibility of the platform. In addition to using a fully customizable solution, it is possible to use IPs to enrich or accelerate our application (filter...).

# ZCU111 caracteristics

The ZCU111 features 8 14-bit [Digital to Analog Converter](https://en.wikipedia.org/wiki/Digital-to-analog_converter) (DAC) that can sample a signal up to 6.554 GSa/s. 

Moreover, the board has 2 RAMs, both of which can be used in this example: 
- 4GB DDR4 Component, attached to Programmable Logic (PL)
- 4GB DDR4 SODIMM (scalable up to 32GB), attached to Processor Subsystem (PS) 

Of course, the card has its limits (which depend among other things on the memory used), which I will detail in another document.

# Project Description

I use **Vivado 2018.3** to design and generate the bitstream and **Pynq 2.6** to run Jupyter Notebooks or C programs.

You will find the project already built in the *build* folder. This can be useful for a first test.

The design sources are however available in the *vivado* folder.

In the folder *pynq_notebook* you will find an example of a notebook that uses the pynq libraries. This one is quite simple to use, but limited for some features. 

In the *python_notebook* folder, you will find an example notebook that uses the standard python libraries. This one is more complicated to use, but allows more flexibility, especially by being able to choose the memory used. 

In the *C* folder, you will find a C code that does the same thing as the python notebook, but in C language (in fact, it is rather the opposite because the python notebook is a simple rewriting of the C code). This one allows a programming closer to the machine, which is easier for me. Moreover, C being much more powerful than python, it can be necessary in some cases. 

Note that the C programs are used in a rather particular way: Indeed, for my application, I upgraded the SODIMM up to the maximum possible (32GB) and I made sure that it is well mapped in /dev/memory, but without the Linux kernel being able to exploit it like classic RAM. More simply, linux still sees 4GB of RAM, but can access the other 28GB of the PS in the same way as the 4GB of the PL.

# Quick Start

You can follow the same instructions as [here](https://github.com/strath-sdr/rfsoc_qpsk#quick-start) and [here](https://github.com/strath-sdr/rfsoc_qpsk#zcu111-setup). 

Specifically, you need to :

- clone the repo directly in the ZCU111 (or clone it on a computer and copy files to the ZCU111) : ```git clone https://github.com/DamienFruleux/ZCU111-AWG```
- load the **pynq_notebook** in Jupyter : ```http://<board_ip_address>:9090/lab```
- and run it :)


# Build the project

In your computer :

- source the Vivado 2018.3 path : ```<path_to_vivado>/2018.3/settings64.sh```
- clone the repo : ```git clone https://github.com/DamienFruleux/ZCU111-AWG```
- move into the vivado folder : ```cd ZCU111-AWG/vivado```
- run ```make```

- load the **pynq_notebook** in Jupyter : ```http://<board_ip_address>:9090/lab```
- and run it :)

# Running the Project

# License

[BSD 3-Clause](https://github.com/DamienFruleux/ZCU111-AWG/blob/main/LICENSE)

# Key Features
(dans chaque exemple)




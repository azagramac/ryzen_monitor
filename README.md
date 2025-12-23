# ryzen_monitor (Fork)

> [!NOTE]
> This is a **maintenance fork** of [AzagraMac/ryzen_monitor](https://github.com/AzagraMac/ryzen_monitor).
> It contains patches for:
> - Newer `ryzen_smu` driver compatibility (v0.1.3+)
> - Scripting support (`-1` single-shot mode)
> 
> Unless you need these specific features, please refer to the [upstream repository](https://github.com/azagramac/ryzen_monitor).

Monitor power information of Ryzen processors via the PM table of the SMU.

This tool is based on the [ryzen_smu](https://github.com/azagramac/ryzen-smu) kernel module for reading the PM Table from the SMU. It is a continuation of the demo-tool provided with that project.

**ryzen_monitor** features support for multiple PM table versions (i.e. multiple bios versions), adds support for Ryzen 5000, and presents more fields to user. It is especially focused around providing a more realistic image of the actual power draw and hence true thermal output of the CPU package.

## Supported CPUs
* Ryzen 5000 series
  * Ryzen 9 5950X
  * Ryzen 9 5900X
  * Ryzen 7 5800X
  * Ryzen 5 5600X 
  * Ryzen 7 5700G
  * Ryzen 5 5600G
* Ryzen 3000 series
  * Ryzen 7 3700X
  * Ryzen 9 3900X
  * Ryzen 9 3950X
  * Other non-Threadripper models will probably work, but are untested

Note: Support also depends on the PM table version that ships with your BIOS and whether ryzen_monitor already knows how to read it.

## Screenshot, CPU Ryzen 9 5950X, Debian 13, Kernel 6.18.2
<img width="700" alt="5950x" src="https://github.com/user-attachments/assets/9eff11c9-93ca-40fa-9962-e02becbe93d1" />

## Building
First install the kernel module from [ryzen_smu](https://github.com/azagramac/ryzen-smu).

Then pull and make **ryzen_monitor**:
```bash
git clone https://github.com/azagramac/ryzen_monitor.git
cd ryzen_monitor/
make

sudo ./src/ryzen_monitor
```
Enjoy!

## About the quality of the provided information
Don't rely on the information given by this tool.

To my knowledge there is no official documentation on how to do this. Everything was created by starring at numbers, a lot of guesswork and finding fragments somewhere on the web. It is possible that some assignments or calculations are incorrect.

This program is provided as is. If anything, it is a toy for the curious. Nothing more. Use it at your own risk.

Regards to Florian Huehn <hattedsquirrel@gmail.com> 

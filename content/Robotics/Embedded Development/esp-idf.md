![[espressif-systems-logo.png|80]]

ESP-IDF is a set of tools to develop directly for the esp32 family of microchips
# Project Structure
- `main/` - represents the main component
- `CMakeLists.txt` - registers main component
- `CMakeFile`-  which compiles entire proejct
- `sdkconfig`- 

# Workflow
- [[#Configure]]
- [[#Build]]
- [[#Flash]]
- [[#Monitor]]
- [[#Debug]]

## Configure
```bash
idf.py create-project NAME
idf.py set-target esp32
idf.py menuconfig
```
## Build

This stage generates 3 binary files:
- partition table

```bash
idf.py all
```
## Flash
```bash
idf.py flash
```
## Monitor
```bash
idf.py -p $PORT monitor
```

## Debug:
**Runtime:**
- GDB
- OpenOCD
- GDB Stub

**Post-mortem**
- Core Dump
- GDB Stub (Panic)


![[memory structure.excalidraw|200]]


## Components
Libraries with extra features:
- **source files, headers and `include` directories**
- **linker fragments (`linker.lf`) - specify memory placement of data and functions of the components** 
- **Embedded Binary and text files -**
- **other pre-compiled libraries -**
- **KConfig -** 
- **Unit Tests (`tests/`) -**


```CmakeLists
# Register a component 

idf_component_register (
	# Source files for this component
	SRCS ./src/my_component.c ./src/algo.c
	#include directories for this component
	INCLUDE_DIRS ./include
	#Other components required by this component
	REQUIRES esp_lcd
	PRIV_REQUIRE driver
	#Linker fragment for this component
	LDFRAGMENTS linker.lf
)
```

```CMakeLists
cmake_minimum_required(VERSION 3.16)

# Pull in IDF Cmake Wrappers
include($ENV{IDF_PATH}/tools/cmake/project.cmake)

#Default directories that are searched for components
# - "esp-idf/components/"
# - "my_project/components/"
# - Declare any extra directories to search for components
set (EXTRA_COMPONENT_DIRS "$ENV(MY_LIBS)/components")

# Declare project
project (my_project)
```


# Relevant Links
- [[FreeRTOS]]
- [[ESP32]]
- [[ESP-IDF Component Registry]]


![[Pasted image 20240907161631.png]]

![[Pasted image 20240907161536.png]]
![[Pasted image 20240907161403.png]]
![[Pasted image 20240907161255.png]]
![[Pasted image 20240907161231.png]]

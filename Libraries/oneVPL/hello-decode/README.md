# `hello-decode` Sample

This sample shows how to use the oneAPI Video Processing Library (oneVPL) to
perform a simple video decode.

| Optimized for    | Description
|----------------- | ----------------------------------------
| OS               | Ubuntu* 18.04; Windows* 10
| Hardware         | Intel® Processor Graphics GEN9 or newer
| Software         | Intel® oneAPI Video Processing Library(oneVPL)
| What You Will Learn | How to use oneVPL to decode an H.265 encoded video file
| Time to Complete | 5 minutes


## Purpose

This sample is a command line application that takes a file containing an H.265
video elementary stream as an argument then decodes it with oneVPL and writes the
decoded output to the file `out.i420` in raw I420 format.


## Key Implementation details

| Configuration     | Default setting
| ----------------- | ----------------------------------
| Target device     | CPU
| Input format      | H.265 video elementary stream
| Output format     | I420
| Output resolution | same as the input


## License

Code samples are licensed under the MIT license. See
[License.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/License.txt) for details.

Third party program Licenses can be found here: [third-party-programs.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/third-party-programs.txt)


## Building the `hello-decode` Program

### On a Linux* System

Perform the following steps:

1. Install the prerequisite software. To build and run the sample, you need to
   install prerequisite software and set up your environment:

   - Intel® oneAPI Base Toolkit for Linux*
   - [CMake](https://cmake.org)

2. Set up your environment using the following command.
   ```
   source <oneapi_install_dir>/setvars.sh
   ```
   Here `<oneapi_install_dir>` represents the root folder of your oneAPI
   installation, which is `/opt/intel/oneapi/` when installed as root, and
   `~/intel/oneapi/` when installed as a normal user.  If you customized the
   installation folder, it is in your custom location.

3. Build the program using the following commands:
   ```
   mkdir build
   cd build
   cmake ..
   cmake --build .
   ```

4. Run the program using the following command:
   ```
   cmake --build . --target run
   ```


### On a Windows* System Using Visual Studio* Version 2017 or Newer

#### Building the program using CMake

1. Install the prerequisite software. To build and run the sample, you need to
   install prerequisite software and set up your environment:

   - Intel® oneAPI Base Toolkit for Windows*
   - [CMake](https://cmake.org)

2. Set up your environment using the following command.
   ```
   <oneapi_install_dir>\setvars.bat
   ```
   Here `<oneapi_install_dir>` represents the root folder of your oneAPI
   installation, which is `C:\Program Files (x86)\Intel\oneAPI\`
   when installed using default options. If you customized the installation
   folder, the `setvars.bat` is in your custom location.  Note that if a
   compiler is not part of your oneAPI installation, you should run in a Visual
   Studio 64-bit command prompt.

3. Build the program using the following commands:
   ```
   mkdir build
   cd build
   cmake ..
   cmake --build .
   ```

4. Run the program using the following command:
   ```
   cmake --build . --target run
   ```


#### Building the program using VS2017 or VS2019 IDE

1. Install the Intel® oneAPI Base Toolkit for Windows*
2. Right-click on the solution file and open using either VS2017 or VS2019 IDE.
3. Right-click on the project in Solution Explorer and select Rebuild.
4. From the top menu, select Debug -> Start without Debugging.

***
Note: You need Base Toolkit 2021.2 or later to build this sample with the IDE.
***


## Running the Sample

### Application Parameters

The instructions given above run the sample executable with the argument
`<sample_dir>/content/cars_128x96.h265`.


### Example of Output

```
Decoding hello-decode/content/cars_128x96.h265 -> out.i420
Decoded 60 frames
```

You can find the output file `out.i420` in the build directory.

You can display the output with a video player that supports raw streams such as
FFplay. You can use the following command to display the output with FFplay:

```
ffplay -video_size 128x96 -pixel_format yuv420p -f rawvideo out.i420
```

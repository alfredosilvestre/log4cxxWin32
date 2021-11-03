# Building log4cxx on Windows
This package offers files to help build log4cxx from the source files found on Apache's website, with Windows environment in mind, and more specifically Visual Studio.  
It consists in of 2 separates elements:
 * a ready-to-use solution for Visual Studio 2017,
 * a CMake file that can be used to build with other version of Visual Studio or even other environments.

The original repository was updated to work with Visual Studio 2017. This is a ready to use solution following the steps of the forked repository.

You will also find prebuilt binaries in the [releases](https://github.com/alfredosilvestre/log4cxxWin32/releases/)

#### Setup
You can use either the Visual Studio 2017 solution in \<msvc15\> or CMake with the CMakeLists.txt in \<cmake\>

## Notes
##### Visual Studio solution
The solution automatically converted from the .dsw found in the log4cxx source package was not usable. The solution proposed here is a clean one built from scratch, using the automatically converted one as a guide.  
log4cxx.dll will be located in msvc17/bin/platform/configuration while apr.lib, xml.lib and apr-util.lib will be found in msvc17/lib/platform/configuration

##### CMake file
The CMakeLists.txt file was initially built to generate a Visual Studio solution very close to the one mentionned above. The idea is to have a cmake base that can be reused for different compilers/systems.  
Because of its history (.dsw -> .sln -> cmake and configure.bat), it is certainly not the optimal way to use CMake for this project. In particular: 
* at least part of the configuration/patch steps could be done in CMake,
* we are not using the existing CMakeLists for apr and apr-util (which are more complete, but also more complex, with options not available through the original configure+.dsw).

##### Tested versions
The content of this project was tested on Windows 7 with
* apr 1.5.2
* apr-util 1.5.4
* log4cxx 0.10.0
* Visual Studio Community 2017
* CMake 3.2.3

### Acknowledgments
A starting point for this work was [this blog's post](https://blog.lextudio.com/2010/09/how-to-build-log4cxx-in-visual-studio-2010/) on how to build log4cxx with Visual Studio 10.

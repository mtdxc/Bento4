Bento4
=====
![CI](https://github.com/axiomatic-systems/Bento4/workflows/CI/badge.svg?branch=master)
           
Bento4 is a C++ class library and tools designed to read and write ISO-MP4 files.
This format is defined in international specifications ISO/IEC 14496-12, 14496-14 and 14496-15.
The format is a derivative of the Apple Quicktime file format, so Bento4 can be used to read and write most Quicktime files as well.

Visit [www.bento4.com](http://www.bento4.com) for details

Features
--------

A number of formats and features based on the ISO-MP4 format and related technologies are also supported, including:

 * MPEG DASH with fragmented MP4 files, as defined in ISO/IEC 23009-1
 * CMAF (Common Media Application Format) as defined in ISO/IEC 23000-19
 * MPEG Common Encryption (CENC) as specified in ISO/IEC 23001-7
 * PIFF (Protected Interoperable File Format): encrypted, fragmented MP4 format specified by Microsoft and used for encrypted HTTP Smooth Streaming.
 * Reading and writing 3GPP and iTunes-compatible metadata.
 * ISMA Encrytion and Decryption as defined in the ISMA E&A specification
 * OMA 2.0 and 2.1 DCF/PDCF Encryption and Decryption as defined in the OMA specifications.
 * ISO-MP4 files profiled as part of the 3GPP family of standards.
 * The UltraViolet (DECE) CFF (Common File Format).
 * Parsing and multiplexing of H.264 (AVC) video and AAC audio elementary streams
 * Support for multiple DRM systems that are compatible with MP4-formatted content (usually leveraging CENC Common Encryption), such as Marlin, PlayReady and Widevine.
 * Support for a wide range of codecs, including H.264 (AVC), H.265 (HEVC), AAC, AC-3, EC-3 (Dolby Digital Plus), AC-4, Dolby ATMOS, DTS, ALAC, and many more.

Design
------

The SDK is designed to be cross-platform. The code is very portable; it can be compiled with any sufficiently modern C++ compiler. The implementation does not rely on any external library. All the code necessary to compile the SDK and tools is included in the standard distribution. The standard distribution contains makefiles for unix-like operating systems, including Linux and Android, project files for Microsoft Visual Studio, and an XCode project for MacOS X and iOS. There is also support for building the library with the SCons build system.


License
-------

The library is Open Source, with a dual-license model. You can find out more about the license on the About Page.
The Developers Page contains specific information on where to obtain the source code and documentation. The Downloads Page contains the links to pre-built SDKs and tools that you can use to get started quickly.

Included Applications
---------------------

The Bento4 SDK includes several command-line applications/tools that are built using the SDK API. These include:

|app name       | description
|---------------|------------------
|mp4info	    | displays high level info about an MP4 file, including all tracks and codec details                                                              
|mp4dump	    | displays the entire atom/box structure of an MP4 file                                                                                           
|mp4edit	    | add/insert/remove/replace atom/box items of an MP4 file                                                                                         
|mp4extract	    | extracts an atom/box from an MP4 file                                                                                                           
|mp4encrypt	    | encrypts an MP4 file (multiple encryption schemes are supported)                                                                                
|mp4decrypt	    | decrypts an MP4 file (multiple encryption schemes are supported)                                                                                
|mp4dcfpackager | encrypts a media file into an OMA DCF file                                                                                                      
|mp4compact	    | converts ‘stsz’ tables into ‘stz2′ tables to create more compact MP4 files                                                                      
|mp4fragment    | creates a fragmented MP4 file from a non-fragmented one or re-fragments an already-fragmented file                                              
|mp4split	    | splits a fragmented MP4 file into discrete files                                                                                                
|mp4tag	        | show/edit MP4 metadata (iTunes-style and others)                                                                                                
|mp4mux	        | multiplexes one or more elementary streams (H264, AAC) into an MP4 file                                                                         
|mp42aac	    | extract a raw AAC elementary stream from an MP4 file                                                                                            
|mp42avc	    | extract a raw AVC/H.264 elementary stream from an MP4 file                                                                                      
|mp42hls	    | converts an MP4 file to an HLS (HTTP Live Streaming) presentation, including the generation of the segments and .m3u8 playlist.
|mp42ts	        | converts an MP4 file to an MPEG2-TS file.
|mp4-dash	    | creates an MPEG DASH output from one or more MP4 files, including encryption.                                                                   
|mp4-dash-clone	| creates a local clone of a remote or local MPEG DASH presentation, optionally encrypting the segments as they are cloned.

mp4info         显示有关MP4文件的高级信息，包括所有tracks和codec的详细信息。
mp4dump         显示MP4文件的整个atom/box结构。
mp4edit         添加/插入/移除/替换 MP4文件的atom/box项。
mp4extract      从MP4文件中提取atom/box
mp4encrypt      加密MP4文件（支持多种加密方案）
mp4decrypt      解密MP4文件（支持多种加密方案）
mp4dcfpackager  将媒体文件加密为OMA DCF文件
mp4compact      将“stsz”表转换为“stz2”表以创建更紧凑的MP4文件
mp4fragment     从非碎片化的MP4文件创建碎片化MP4文件。
mp4split        将碎片化的MP4文件拆分为离散文件
mp4tag          显示/编辑MP4元数据（iTunes样式和其他样式）
mp4mux          将一个或多个基本流（H264/AVC、H265/HEVC、AAC）多路复用到MP4文件中
mp42aac         从MP4文件中提取原始AAC基本流
mp42avc         从MP4文件中提取原始AVC/H.264基本流
mp42hls         将MP4文件转换为HLS（HTTP Live Streaming）演示文稿，包括生成片段和.m3u8播放列表以及AES-128和SAMPLE-AES（用于公平播放）加密。这可以作为苹果mediafilesegmenter工具的替代品。
mp42ts          将MP4文件转换为MPEG2-TS文件。
mp4dash         从一个或多个MP4文件（包括加密）创建MPEG破折号输出。作为一种选择，还可以同时生成带有MP4片段的HLS播放列表，允许将单个流用作DASH和HLS。这是一个功能齐全的MPEG DASH/HLS打包机。
mp4dashclone    创建远程或本地MPEG破折号演示文稿的本地克隆，并在克隆片段时对其进行加密。
mp4hls          从一个或多个MP4文件创建多比特率HLS主播放列表，包括对加密和仅I帧播放列表的支持。此工具在内部使用“mp42hls”低级工具，因此该低级工具支持的所有选项也都可用。这可以作为苹果variantplaylistcreator工具的替代品。

Building
--------

The code can be built either by using the pre-configured IDE project files (Mac OSX, iOS and Windows), or compiled/cross-compiled using the SCons build system or CMake, or compiled using Make.
Target platform specific build files and configurations are located under subdirectories Buid/Targets/xxxx where xxxx takes the form ```<architecture>-<vendor>-<os>```. For example, the Linux x86 target specific files are located under ```Build/Targets/x86-unknown-linux```. The XCode project files for Mac OSX are located under ```Build/Targets/universal-apple-macosx```.

### Mac OSX and iOS using XCode
Open the XCode project file Build/Targets/universal-apple-macosx/Bento4.xcodeproj and build

### Windows using Visual Studio
Open the Visual Studio solution file Build/Targets/x86-microsoft-win32-vs2010/Bento4.sln and build

### On Linux and other platforms, Using CMake
CMake can generate Makefiles, Xcode project files, or Visual Studios project files.

#### CMake/Make

	mkdir cmakebuild
	cd cmakebuild
	cmake -DCMAKE_BUILD_TYPE=Release ..
	make

#### CMake/Xcode

	mkdir cmakebuild
	cd cmakebuild
	cmake -G Xcode ..
    cmake --build . --config Release

#### CMake/Visual Studio
	mkdir cmakebuild
	cd cmakebuild
	cmake -DCMAKE_BUILD_TYPE=Release ..
    cmake --build . --config Release

#### CMake for Android NDK
    mkdir cmakebuild
    cd cmakebuild
    cmake -DCMAKE_TOOLCHAIN_FILE=$NDK/build/cmake/android.toolchain.cmake -DANDROID_ABI=$ABI -DANDROID_NATIVE_API_LEVEL=$MINSDKVERSION ..
    make

    See https://developer.android.com/ndk/guides/cmake for details on the choice of ABI and other parameters.
    
    Where $NDK is set to the directory path where you have installed the NDK, $ABI is the Android ABI (ex: arm64-v8a) and $MINSDKVERSION is the minimum SDK version (ex: 23)

### On Linux and other platforms, using SCons (deprecated)
Make sure you the the SCons build tool installed on your host machine (http://www.scons.org).
To build the Debug configuration, simply enter the command:

```scons -u```

in a terminal from any directory (either from the top level directory where you downloaded the Bento4 distribution, or from the Build/Targets/xxx subdirectory for your specific target).

To build the Release configuration, use the command:

```scons -u build_config=Release```

To cross-compile for a target other than your host architecture, specify target=xxxx as an argument to the scons build command.

Example:

```scons -u build_config=Release target=x86_64-unknown-linux```

### Using Make
From a command shell, go to your build target directory.

For Debug builds:
	```make```

For Release builds:
```make AP4_BUILD_CONFIG=Release```

## Installing Bento4 (vcpkg)

Alternatively, you can build and install Bento4 using [vcpkg](https://github.com/Microsoft/vcpkg/) dependency manager:

    git clone https://github.com/Microsoft/vcpkg.git
    cd vcpkg
    ./bootstrap-vcpkg.sh
    ./vcpkg integrate install
    ./vcpkg install bento4

The Bento4 port in vcpkg is kept up to date by Microsoft team members and community contributors. If the version is out of date, please [create an issue or pull request](https://github.com/Microsoft/vcpkg) on the vcpkg repository.

Release Notes
-------------

### 1.6.0-638
  * support multi-bitrate audio
  * new docs using MkDocs
  * add av1 files and remove deprecated option from vs2019 build
  * add AV1 support
  * better handling of USAC signaling
  * add UTF-8 support on Windows
  * fix LGTM warnings
  * account for last sample when at EOS
  * new inspector API
  * bug fixes

### 1.6.0-636
Dolby Vision encryption now properly encrypts in a NAL-unit-aware mode

### Previous releases
(no seaparate notes, please refer to commit logs)

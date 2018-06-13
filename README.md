# Prebuild LGPL-2.1 FFmpeg with OpenH264 for Windows 64bit
This project provides Prebuild LGPL v2.1 FFmpeg 3.4 binaries cross compiled with MinGW for Windows 64bit with OpenH264 to support H264 encoding.
The binaries are located under `bin/` the used source files with `.lib` files under `source/`. Source is original master branch and was not modified.

## How to Use
If you want to use ffmpeg from the cli you can drop the [release openh264.dll](https://github.com/cisco/openh264/releases/tag/v1.7.0) into the bin folder and rename it to: `libopenh264.dll`

If you want to use ffmpeg as a library you need to do the step above and use `source/` as include folder. You also need to link against the following libs:  
`avcodec.lib;avdevice.lib;avfilter.lib;avformat.lib;avutil.lib;swresample.lib;swscale.lib`


## Configure
The following configure arguments was used when building FFmpeg:
`--enable-shared --disable-static --arch=x86_64 --target-os=mingw32 --cross-prefix=x86_64-w64-mingw32- --pkg-config=pkg-config --enable-libopenh264`

## License
The binaries are under the GNU Lesser General Public License version 2.1 or later. However the source may contain files that are Licensed under GPL 
but theese files are NOT included in the binarys. For more information check https://github.com/FFmpeg/FFmpeg/blob/master/LICENSE.md

## Legal notice
As already mentioned in [FFmpeg License and Legal Considerations](https://www.ffmpeg.org/legal.html) FFmpeg is a colletion of dozens of librarys and algorithms.
It may be the case that some parts of some librarys fall under specifiy patent rights. Using h264, mpeg4 or mp4 may require license fees if used in big scales.

## Motivation
I spend a lot of time trying to compile FFmpeg for Windows by following the offical [CompilationGuide](https://trac.ffmpeg.org/wiki/CompilationGuide)
Some parts of the guides are a bit outdated with dead links and wrong arguments so nothing works as you would expect.

### Enviroment
If you try to compile on Windows using MinGW or Cygwin you will spend a lot of time time alone for setting up the enviroment.
Cross compiling under Linux is more easy but you need to have access to a machine with a toolchain for cross compiling.
### License
Most of the prebuild binaries (except OpenCV) use libx264 and therefore the GPL license. This might be unwanted for some project.
### OpenH264
OpenH264 is under BSD license and used as a replacement for libx264 so you can still encode h264.


## Need Help?
If you need help compiling FFmpeg you can contact me, unlike other people I won't take 200$ for it and instead help for free if I can. 

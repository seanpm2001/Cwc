
# The CWeet compilation " [![Screen Shot](Tools/Cwc_small.png)](https://github.com/Honera/Cwc/blob/master/Tools/Cwc_small.png) "

Cwc is a **front-end** C++ compiler, for any programmer who wants to simplify life.

It can be use as a direct remplacement of GCC or Clang. 
Say goodbye to the huge mess of C++ compilation. This tool will become your best friend.

It can be see as an intelligent compiler, it is use in the same way, but with additions. It can be connect to any IDE and enjoy all its features.

Cwc, is not a compiler in itself, like a chameleon, he redirects inputs / outputs with any back-end compiler


## Command line:

The main principle is to send several commands simultaneously, with the following separators:

`|` : Allows you to send commands simultaneously in multi-process. The output is guaranteed to be the same order, so it's always the same result that is displayed

`>`: To make sequences, it will be necessary to wait for previous orders

So we can do something like **"buildObj `|` buildObj `>` Link"**

Example: **"-c Src1.cpp -o Src1.o `|` -c Src2.cpp -o Src2.o `>` -o App.exe Src1.o Src2.o"**


## Main Feature

### Modular
All backend compiler or lib that will require for a project will be automaticly downloaded and will have is own compilation toolchain and arguments


### Speed
To speed up the compilation it is important not to recompile the already created object files.
Many IDEs are unable to correctly detect changes and often result in an erroneous executable, some of which has not been up to date, causing serious errors that are difficult to pinpoint.

Cwc have a concrete detection, it checks all the dependencies of each file if there is a change, as well as any change of command line. A command like "clean" is thus practically obsolete.

### Compilation by folder:
It is possible to send directory in command line, it will process all the files inside which greatly simplify the command list.

### Accepts the variables:
We can insert variables in our commands, using parentheses ()
Several important variables are predefined to simplify the management of the files according to the type of build (x86, x64, Debug, O2, O3) which requires different.

### Sanitizer:
Connect to DrMemory, you can comb through all possible memory errors


# Screen

 [![Screen Shot](Tools/Screen.png)](https://github.com/Honera/Cwc/blob/master/Tools/Screen.png)
 
 
 # Supported Export Platform

Cwc can export binary to any platform without any modification of your makefile or your code

Here are the functional toolchain for now:

* Windows           ([LibRT](https://github.com/VLiance/LibRT))
* Web -> Emscriptem ([WebRT](https://github.com/VLiance/WebRT))

TODO:

* Android           ([DroidRT](https://github.com/VLiance/DroidRT))
* IOS				([DroidRT](https://github.com/VLiance/IRT))

Any other custom toolchain can be add easily with a Github repo, possibilities is limitless

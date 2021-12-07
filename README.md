# tdlib for Raspberry

A plug&play **libtdjson.so v1.7.9** built for **Raspberry Pi**

## How to build

If you want to build by your own follow these steps:

`TDLib` depends on:

* C++14 compatible compiler (Clang 3.4+, GCC 4.9+, MSVC 19.0+ (Visual Studio 2015+), Intel C++ Compiler 17+)
* OpenSSL
* zlib
* gperf (build only)
* CMake (3.0.2+, build only)

```bash
git clone https://github.com/tdlib/td.git
cd td
rm -rf build
mkdir build

sudo nano CMakeLists.txt
```

- Now add this instruction

```bash
 set(CMAKE_CXX_LINK_FLAGS "${CMAKE_CXX_LINK_FLAGS} -latomic")
```

- Now you are able to build

```bash
cd build
cmake -DCMAKE_BUILD_TYPE=Release
cd ..
php SplitSource.php
cd build
cmake --build . --target install
cd ..
php SplitSource.php --undo
cd ..
ls -l td/tdlib
```
## Tips

You may have some issues due to low memory on your board: try to increaseyour SWAP

## Compatibility
Tested on: 
- **Raspberry Pi 3B+ 
Linux raspberrypi 5.4.51-v7+ #1333 SMP Mon Aug 10 16:45:19 BST 2020 armv7l GNU/Linux** 

- Language **Python**

# slint-compiler


sudo nano /usr/lib/pkgconfig/slint.pc

prefix=/home/maik/Slint-cpp-1.17.1-Linux-x86_64
exec_prefix=${prefix}
libdir=${prefix}/lib
includedir=${prefix}/include/slint

Name: Slint
Description: Slint C++ UI Toolkit
Version: 1.17.1
Libs: -L${libdir} -lslint_cpp -Wl,-rpath,${libdir}
Cflags: -I${includedir}


pkg-config --cflags slint
pkg-config --libs slint



# Compilation

slint-compiler ui.slint -o ui.h

g++ -std=c++20 main.cpp \
    $(pkg-config --cflags --libs slint) \
    -o app

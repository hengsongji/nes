# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add.library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

add_library( # Specifies the name of the library.
        NesSimon
        # Sets the library as a shared library.
        SHARED
        # Provides a relative path to your source file(s).
        src/main/jni/com_falcon_nester_NesSimu.c
        src/main/jni/InfoNES_System_Android.c
        src/main/jni/buffersoundpool.c
        src/main/jni/nes/c/InfoNES.c
        src/main/jni/nes/c/InfoNES_pAPU.c
        src/main/jni/nes/c/InfoNES_Mapper.c
        src/main/jni/nes/c/K6502.c)

target_link_libraries( # Specifies the target library.
        NesSimon
        # Links the log library to the target library.
        log)

target_link_libraries(
        NesSimon
        jnigraphics)

target_link_libraries(
        NesSimon
        OpenSLES)

# Specifies a path to native header files.
include_directories(src/main/jni/nes/h/)
include_directories(src/main/jni/)
cmake_minimum_required (VERSION 3.15.4)

project(lua)

set(BUILD_TARGET_ROOT_DIR "${PROJECT_SOURCE_DIR}/target")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG "${BUILD_TARGET_ROOT_DIR}/lib_d/")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE "${BUILD_TARGET_ROOT_DIR}/lib/")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG "${BUILD_TARGET_ROOT_DIR}/bin_d/")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE "${BUILD_TARGET_ROOT_DIR}/bin/")

set(library_source
        "lapi.c"
        "lauxlib.c"
        "lbaselib.c"
        "lbitlib.c"
        "lcode.c"
        "lcorolib.c"
        "lctype.c"
        "ldblib.c"
        "ldebug.c"
        "ldo.c"
        "ldump.c"
        "lfunc.c"
        "lgc.c"
        "linit.c"
        "liolib.c"
        "llex.c"
        "lmathlib.c"
        "lmem.c"
        "loadlib.c"
        "lobject.c"
        "lopcodes.c"
        "loslib.c"
        "lparser.c"
        "lstate.c"
        "lstring.c"
        "lstrlib.c"
        "ltable.c"
        "ltablib.c"
        "ltm.c"
        "lundump.c"
        "lutf8lib.c"
        "lvm.c"
        "lzio.c"
        # HEAD
        "lapi.h"
        "lcode.h"
        "lctype.h"
        "ldebug.h"
        "ldo.h"
        "lfunc.h"
        "lgc.h"
        "llex.h"
        "llimits.h"
        "lmem.h"
        "lobject.h"
        "lopcodes.h"
        "lparser.h"
        "lprefix.h"
        "lstate.h"
        "lstring.h"
        "ltable.h"
        "ltm.h"
        "lundump.h"
        "lvm.h"
        "lzio.h"
        "lauxlib.h"
        "lua.h"
        "lua.hpp"
        "luaconf.h"
        "lualib.h"
        )

add_library(lua STATIC ${library_source})
set(liblua_static_include "${CMAKE_CURRENT_SOURCE_DIR}/src")
target_include_directories(lua PUBLIC ${liblua_static_include})

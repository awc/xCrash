SET(xcrash_common_sources
        src/xcc_b64.c
        src/xcc_fmt.c
        src/xcc_libc_support.c
        src/xcc_meminfo.c
        src/xcc_signal.c
        src/xcc_unwind.c
        src/xcc_unwind_clang.c
        src/xcc_unwind_libcorkscrew.c
        src/xcc_unwind_libunwind.c
        src/xcc_util.c)
ADD_LIBRARY(xcrash_common STATIC ${xcrash_common_sources})
TARGET_INCLUDE_DIRECTORIES(xcrash_common PUBLIC include)
TARGET_COMPILE_OPTIONS(xcrash_common
        PRIVATE
        -std=c11
        -Weverything
        -Werror
        -O0)

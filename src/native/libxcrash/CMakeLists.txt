SET(xcrash_sources
        src/xc_common.c
        src/xc_crash.c
        src/xc_dl.c
        src/xc_fallback.c
        src/xc_jni.c
        src/xc_test.c
        src/xc_trace.c
        src/xc_util.c)
ADD_LIBRARY(xcrash SHARED ${xcrash_sources})
TARGET_INCLUDE_DIRECTORIES(xcrash PRIVATE include)
TARGET_COMPILE_OPTIONS(xcrash
        PRIVATE
        -std=c11
        -Weverything
        -Werror
        -fvisibility=hidden)
TARGET_LINK_LIBRARIES(xcrash xcrash_common ${libdl} ${liblog})

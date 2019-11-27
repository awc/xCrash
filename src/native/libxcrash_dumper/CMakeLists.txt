SET(xcrash_dumper_sources
        src/xcd_arm_exidx.c
        src/xcd_core.c
        src/xcd_dwarf.c
        src/xcd_elf.c
        src/xcd_elf_interface.c
        src/xcd_frames.c
        src/xcd_map.c
        src/xcd_maps.c
        src/xcd_md5.c
        src/xcd_memory.c
        src/xcd_memory_buf.c
        src/xcd_memory_file.c
        src/xcd_memory_remote.c
        src/xcd_process.c
        src/xcd_regs_arm.c
        src/xcd_regs_arm64.c
        src/xcd_regs_x86.c
        src/xcd_regs_x86_64.c
        src/xcd_sys.c
        src/xcd_thread.c
        src/xcd_util.c)
ADD_LIBRARY(xcrash_dumper SHARED ${xcrash_dumper_sources})
TARGET_INCLUDE_DIRECTORIES(xcrash_dumper PRIVATE include)
TARGET_COMPILE_OPTIONS(xcrash_dumper
        PRIVATE
        -std=c11
        -Weverything
        -Werror
        -fvisibility=hidden)
TARGET_LINK_LIBRARIES(xcrash_dumper PRIVATE xcrash_common lzma ${libdl} ${liblog})

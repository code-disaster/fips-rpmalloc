#
# project: fips-rpmalloc
#

fips_begin_lib(rpmalloc)
    include_directories(rpmalloc/rpmalloc)
    fips_dir(rpmalloc/rpmalloc)
    fips_files(rpmalloc.h rpmalloc.c)
    if (RPMALLOC_OVERRIDE_STDLIB)
        fips_files(malloc.c)
    endif()
    if (RPMALLOC_OVERRIDE_NEW)
        fips_files(new.cc)
    endif()
fips_end_lib()

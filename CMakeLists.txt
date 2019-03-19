if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup()
    fips_project(fips-libigl)
endif()

if ((FIPS_MACOS OR FIPS_WINDOWS OR FIPS_LINUX) AND NOT (FIPS_RASPBERRYPI OR FIPS_OSX_USE_ARC OR FIPS_UWP))

    # fips_begin_lib(libigl)
    # include_directories(libigl/include)
    # fips_src(libigl/include/igl NO_RECURSE)
    # add_definitions(-DIGL_STATIC_LIBRARY -DNOMINMAX -DM_PI)


    #  fips_end_lib()

    #      ### Compilation flags: adapt to your needs ###
    # if(MSVC)
    #   set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /MP /bigobj") ### Enable parallel compilation
    #    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR} )
    #    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR} )
    #   set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /w") # disable all warnings (not ideal but...)
    # else()
    #   # set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11") #### Libigl requires a modern C++ compiler that supports c++11
    #   # set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "../" )
    #   set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -w") # disable all warnings (not ideal but...)
    # endif()

    set(PUGIXML_HEADER_ONLY 1)


endif()

if (NOT FIPS_IMPORT)
    fips_finish()
endif()
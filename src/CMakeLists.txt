set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
add_library(spruce SHARED spruce.cc)

# make the header public
# install it to include/hello
pods_install_headers(spruce.hh DESTINATION spruce)

# make the library public
pods_install_libraries(spruce)

# uncomment these lines to link against another library via pkg-config
#set(REQUIRED_PACKAGES pkg_a pkg_b)
#pods_use_pkg_config_packages(hello ${REQUIRED_PACKAGES})

# create a pkg-config file for the library, to make it easier for other
# software to use.
pods_install_pkg_config_file(spruce
    CFLAGS
    LIBS -lspruce
    REQUIRES ${REQUIRED_PACKAGES}
    VERSION 0.0.1)

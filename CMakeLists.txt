cmake_minimum_required(VERSION 3.5.1)

project(libvsd)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CUDA_TOOLKIT_ROOT_DIR /usr/local/cuda)

# find packages
find_package(Eigen3 REQUIRED)
find_package(CUDA QUIET REQUIRED)

set(PROTOBUF_INCLUDE_DIRS /usr/local/include/google)

set(PROTOBUF_LIBRARIES /usr/local/lib/libprotobuf.so)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/modules)

include_directories(include)

include_directories(/usr/local/include/google/tensorflow
                    ${PROTOBUF_INCLUDE_DIRS}
                    ${EIGEN3_INCLUDE_DIRS}
                    /home/hejia/Library_Sources/3rd_library/tensorflow/bazel-tensorflow/external/nsync/public
                    /usr/local/include
                    /usr/local/cuda/include)

link_directories(/usr/local/lib)

add_subdirectory(src)




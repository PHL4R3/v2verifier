cmake_minimum_required(VERSION 3.10)
project(v2verifier)

set(SOURCE_FILES
    src/main.cpp
    src/Vehicle.cpp
    src/v2vcrypto.cpp
    src/bsm.cpp
    src/threading.cpp)

find_package(OpenSSL REQUIRED)

add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} OpenSSL::Crypto)
target_include_directories(${PROJECT_NAME} PRIVATE ${PROJECT_SOURCE_DIR}/include)
cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

project(cppzmq-examples CXX)

# place binaries and libraries according to GNU standards

include(GNUInstallDirs)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ../src/)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ../src/)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ../src/)

find_package(Threads)
find_package(cppzmq)

add_executable(
    pubsub_multithread_inproc
    src/pubsub_multithread_inproc.cpp
)
target_link_libraries(
    pubsub_multithread_inproc
    PRIVATE cppzmq ${CMAKE_THREAD_LIBS_INIT}
)

add_executable(
    hello_world
    src/hello_world.cpp
)
target_link_libraries(
    hello_world
    PRIVATE cppzmq ${CMAKE_THREAD_LIBS_INIT}
)

add_executable(
    publisher
    src/publisher.cpp
)
target_link_libraries(
    publisher
    PRIVATE cppzmq ${CMAKE_THREAD_LIBS_INIT}
)

add_executable(
    subscriber
    src/subscriber.cpp
)
target_link_libraries(
    subscriber
    PRIVATE cppzmq ${CMAKE_THREAD_LIBS_INIT}
)
# add_executable(
#     multipart_messages
#     multipart_messages.cpp
# )
# target_link_libraries(
#     multipart_messages
#     PRIVATE cppzmq ${CMAKE_THREAD_LIBS_INIT}
# )
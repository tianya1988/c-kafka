cmake_minimum_required(VERSION 3.13)
project(c_kafka C)

set(CMAKE_C_STANDARD 11)

include_directories(/usr/local/include/librdkafka)

link_directories(/usr/local/lib)

add_executable(c_kafka
        my_producer.c)

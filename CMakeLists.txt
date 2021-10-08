cmake_minimum_required(VERSION 3.11)

project(boost_headers 	VERSION 1.77.0
                  		DESCRIPTION "Boost headers"
                  		LANGUAGES CXX)

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(${PROJECT_NAME} INTERFACE  boost/)
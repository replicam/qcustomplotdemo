cmake_minimum_required(VERSION 3.7.0)

project(qcustomplotdemo VERSION 1.0.0 LANGUAGES CXX)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  set(CMAKE_BUILD_TYPE "RelWithDebInfo")
endif()

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 COMPONENTS Widgets PrintSupport REQUIRED)

add_executable(qcustomplotdemo
    qcustomplot.h qcustomplot.cpp
    mainwindow.h mainwindow.cpp
    main.cpp
)

target_link_libraries(qcustomplotdemo
  Qt6::Widgets Qt6::PrintSupport
  )

install(TARGETS qcustomplotdemo)

cmake_minimum_required(VERSION 2.8.3)
project(qt_example)

add_definitions(-std=c++11)

find_package(Qt4 COMPONENTS QtCore QtGui REQUIRED)

include(${QT_USE_FILE})
include_directories(include)

add_definitions(-DQT_NO_KEYWORDS)

qt4_wrap_cpp(MOC_FILES
    include/qt_example.h
)

add_executable(qt_example ${MOC_FILES} src/qt_example.cpp src/qt_example_main.cpp)
target_link_libraries(qt_example ${QT_LIBRARIES})
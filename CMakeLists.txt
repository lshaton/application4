cmake_minimum_required(VERSION 3.10)
project(application4 C)

set(CMAKE_C_STANDARD 11)

include_directories(.)

add_executable(application4
        app-menu.ui
        exampleapp.c
        exampleapp.gresource.xml
        exampleapp.h
        exampleappwin.c
        exampleappwin.h
        main.c
        Makefile.example
        meson.build
        resources.c
        window.ui)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

add_definitions(${GTK3_CFLAGS_OTHER})

target_link_libraries(application4 ${GTK3_LIBRARIES})
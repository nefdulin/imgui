cmake_minimum_required(VERSION 3.20)
project(imgui CXX C)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY  "${CMAKE_BINARY_DIR}/lib")

add_library(imgui STATIC
        imgui.cpp
        imgui.h
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_impl_opengl3_loader.h
        imgui_impl_glfw.h
        imgui_impl_glfw.cpp
        imgui_impl_opengl3.h
        imgui_impl_opengl3.cpp
        imgui_internal.h
        imgui_tables.cpp
        imgui_widgets.cpp
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
        )
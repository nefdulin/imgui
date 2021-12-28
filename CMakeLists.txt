cmake_minimum_required(VERSION 3.20)
project(imgui CXX C)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY  "${CMAKE_BINARY_DIR}/lib")

# I don't know about this, could be a better way to do this
if (OS_MACOSX)
    include_directories(${CMAKE_CURRENT_SOURCE_DIR}../glfw/include)

    set(IMGUI_IMPL_SRC
            backends/imgui_impl_opengl3_loader.h
            backends/imgui_impl_glfw.h
            backends/imgui_impl_glfw.cpp
            backends/imgui_impl_opengl3.h
            backends/imgui_impl_opengl3.cpp)
endif()

add_library(imgui STATIC
        imgui.cpp
        imgui.h
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_internal.h
        imgui_tables.cpp
        imgui_widgets.cpp
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
        ${IMGUI_IMPL_SRC}
        )
cmake_minimum_required(VERSION 3.12)
project(imgui CXX)

# dear imgui uses the C++ virtual interfaces for DirectX
remove_definitions(-DCINTERFACE)

set(IMGUI_HEADERS
        imconfig.h
        imgui.h
        imgui_internal.h
        backends/imgui_impl_dx9.h
        misc/cpp/imgui_stdlib.h
)
set(IMGUI_SOURCES
        imgui.cpp
        imgui_draw.cpp
        imgui_tables.cpp
        imgui_widgets.cpp
        imgui_demo.cpp
        backends/imgui_impl_dx9.cpp
        misc/cpp/imgui_stdlib.cpp
)

add_library(imgui STATIC ${IMGUI_HEADERS} ${IMGUI_SOURCES})
target_include_directories(imgui PRIVATE ${PROJECT_SOURCE_DIR})

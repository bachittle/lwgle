cmake_minimum_required(VERSION 3.10)
project(imgui LANGUAGES CXX)

set(IMGUI_DIR "imgui")

add_library(imgui STATIC 
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/imgui_widgets.cpp
    ${IMGUI_DIR}/imgui_demo.cpp
    ${IMGUI_DIR}/imgui_draw.cpp
    ${IMGUI_DIR}/imgui_tables.cpp

    ${IMGUI_DIR}/backends/imgui_impl_glfw.cpp
    ${IMGUI_DIR}/backends/imgui_impl_opengl3.cpp
)
target_include_directories(imgui PUBLIC ${IMGUI_DIR})

# My personal implementation is only using glfw and opengl
# Subject to change. 

# glfw
target_link_libraries(imgui PUBLIC glfw)

# # opengl
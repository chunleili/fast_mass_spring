cmake_minimum_required(VERSION 3.23)
project(fast_mass_spring)

set(SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/fast_mass_spring/source)
add_executable(main "")
target_include_directories(main PUBLIC fast_mass_spring/source)
target_sources(main PUBLIC    
    fast_mass_spring/source/anttweakbar_wrapper.cpp
    fast_mass_spring/source/camera.cpp
    fast_mass_spring/source/constraint.cpp
    fast_mass_spring/source/fps.cpp
    fast_mass_spring/source/glsl_wrapper.cpp
    fast_mass_spring/source/io_mesh.cpp
    fast_mass_spring/source/main.cpp
    fast_mass_spring/source/math_headers.cpp
    fast_mass_spring/source/mesh.cpp
    fast_mass_spring/source/primitive.cpp
    fast_mass_spring/source/scene.cpp
    fast_mass_spring/source/simulation.cpp
    fast_mass_spring/source/stb_image.c
    fast_mass_spring/source/stb_image_write.c
    fast_mass_spring/source/tinyxml2.cpp)

# external libraries
set(EXTERN ${CMAKE_CURRENT_SOURCE_DIR}/external_dependencies)
find_package(OpenGL REQUIRED)
target_link_libraries(main PUBLIC OpenGL::GL)

target_include_directories(main PUBLIC ${EXTERN}/AntTweakBar/include)
target_include_directories(main PUBLIC ${EXTERN}/Eigen)
target_include_directories(main PUBLIC ${EXTERN}/freeglut/include)
target_include_directories(main PUBLIC ${EXTERN}/glew/include)
target_include_directories(main PUBLIC ${EXTERN}/glm)

target_link_directories(main PUBLIC ${EXTERN}/AntTweakBar/lib
                                     ${EXTERN}/freeglut/lib/x64
                                     ${EXTERN}/glew/lib)

target_link_libraries(main PUBLIC ${EXTERN}/glew/lib/glew32.lib)
target_link_libraries(main PUBLIC ${EXTERN}/AntTweakBar/lib/AntTweakBar64.lib)
target_link_libraries(main PUBLIC ${EXTERN}/freeglut/lib/x64/freeglut.lib)
target_link_libraries(main PUBLIC ${EXTERN}/glew/lib/glew32mx.lib)

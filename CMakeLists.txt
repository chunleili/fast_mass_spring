cmake_minimum_required(VERSION 3.23)
project(fast_mass_spring)

add_executable(main fast_mass_spring/source/main.cpp)
set(SRC_DIR ${PROJECT_SOURCE_DIR}/source)
file(GLOB_RECURSE SRC_FILES ${SRC_DIR}/*.cpp ${SRC_DIR}/*.h)
target_include_directories(main PUBLIC ${SRC_DIR})
target_sources(main PRIVATE ${SRC_FILES})


# external libraries
set(EXTERN ${CMAKE_CURRENT_SOURCE_DIR}/external_dependencies)
find_package(OpenGL REQUIRED)
target_link_libraries(main PUBLIC OpenGL::GL)
target_include_directories(main PUBLIC ${EXTERN}/Eigen)
target_include_directories(main PUBLIC ${EXTERN}/glm)
target_include_directories(main PUBLIC ${EXTERN}/AntTweakBar/include)
target_include_directories(main PUBLIC ${EXTERN}/freeglut/include)
target_include_directories(main PUBLIC ${EXTERN}/glew/include)

target_link_libraries(main PUBLIC ${EXTERN}/AntTweakBar/lib/AntTweakBar64.lib)
target_link_libraries(main PUBLIC ${EXTERN}/freeglut/lib/x64/freeglut.lib)
target_link_libraries(main PUBLIC ${EXTERN}/glew/lib/glew32.lib)
target_link_libraries(main PUBLIC ${EXTERN}/glew/lib/glew32mx.lib)

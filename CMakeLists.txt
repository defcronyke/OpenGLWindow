cmake_minimum_required(VERSION 3.7)
project(OpenGLWindow)
set (CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${OpenGLWindow_SOURCE_DIR}/cmake-modules")

find_package(SDL2 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(GLM REQUIRED)

include_directories(OpenGLWindow
  include
  ${SDL2_INCLUDE_DIR}
  ${OPENGL_INCLUDE_DIR}
  ${GLEW_INCLUDE_DIRS}
  ${GLM_INCLUDE_DIR}
)
# add_library(OpenGLWindow SHARED
#   src/SolarSemiotics.cpp
# )
add_executable(opengl-window
  src/main.cpp
  src/LoadShaders.cpp
)
target_link_libraries(opengl-window
  # OpenGLWindow
  ${SDL2_LIBRARY}
  ${SDL2_IMAGE_LIBRARY}
  ${OPENGL_LIBRARIES}
  ${GLEW_LIBRARIES}
  ${GLM_LIBRARIES}
)

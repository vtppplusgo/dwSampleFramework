cmake_minimum_required(VERSION 3.8 FATAL_ERROR)

project("dwSampleFramework")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/lib")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/lib")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)

set(DWSFW_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/include")
set(GLFW_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/external/glfw/include")
set(GLM_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/external/glm/glm")
set(STB_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/external/stb")
set(IMGUI_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/external/imgui")
set(JSON_INCLUDE_DIRS "${PROJECT_SOURCE_DIR}/external/json/single_include/nlohmann")

include_directories("${DWSFW_INCLUDE_DIRS}"
                    "${GLM_INCLUDE_DIRS}"
                    "${STB_INCLUDE_DIRS}"
                    "${IMGUI_INCLUDE_DIRS}"
                    "${JSON_INCLUDE_DIRS}"
                    "${GLFW_INCLUDE_DIRS}")

add_subdirectory(external/glfw)
add_subdirectory(src)
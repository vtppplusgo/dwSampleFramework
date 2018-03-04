cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# find_package(OpenGL REQUIRED)

set(DWSFW_SOURCE ${PROJECT_SOURCE_DIR}/external/imgui/imgui.cpp
			     ${PROJECT_SOURCE_DIR}/external/imgui/imgui_demo.cpp
			     ${PROJECT_SOURCE_DIR}/external/imgui/imgui_draw.cpp
			     ${PROJECT_SOURCE_DIR}/src/imgui_impl_glfw_gl3.cpp
			     ${PROJECT_SOURCE_DIR}/src/timer.cpp
			     ${PROJECT_SOURCE_DIR}/src/logger.cpp
			     ${PROJECT_SOURCE_DIR}/src/utility.cpp
			     ${PROJECT_SOURCE_DIR}/src/camera.cpp
				 ${PROJECT_SOURCE_DIR}/src/application.cpp)

set(DWSFW_HEADERS ${PROJECT_SOURCE_DIR}/include/macros.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/imconfig.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/imgui.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/imgui_internal.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/stb_rect_pack.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/stb_textedit.h
				  ${PROJECT_SOURCE_DIR}/external/imgui/stb_truetype.h
				  ${PROJECT_SOURCE_DIR}/include/imgui_impl_glfw_gl3.h
				  ${PROJECT_SOURCE_DIR}/include/camera.h
				  ${PROJECT_SOURCE_DIR}/include/timer.h
				  ${PROJECT_SOURCE_DIR}/include/application.h
				  ${PROJECT_SOURCE_DIR}/include/logger.h
				  ${PROJECT_SOURCE_DIR}/include/utility.h
				  ${PROJECT_SOURCE_DIR}/src/gl_core_4_5.h)

add_library(dwSampleFramework ${DWSFW_HEADERS} ${DWSFW_SOURCE})				

set_target_properties( dwSampleFramework
    				   PROPERTIES
    				   ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/lib"
    				   LIBRARY_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/lib"
    				   RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin" )

# target_link_libraries(dwSampleFramework ${OPENGL_LIBRARIES})
target_link_libraries(dwSampleFramework glfw)
set(SOURCE_DIR "Source")

set(SOURCES
    main.cpp
)

# Add the executable target
add_executable(A1Student ${SOURCES})
set_target_properties(A1Student PROPERTIES OUTPUT_NAME prog.x)
target_include_directories(A1Student PRIVATE ${PROJECT_SOURCE_DIR}/external/raylib/src)
target_include_directories(A1Student PRIVATE ${PROJECT_SOURCE_DIR}/external/)



target_link_libraries(A1Student imgui)
target_link_libraries(A1Student raylib)

# Checks if OSX and links appropriate frameworks (only required on MacOS)
if (APPLE)
    target_link_libraries(${PROJECT_NAME} "-framework IOKit")
    target_link_libraries(${PROJECT_NAME} "-framework Cocoa")
    target_link_libraries(${PROJECT_NAME} "-framework OpenGL")
endif()






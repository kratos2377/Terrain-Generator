add_executable(main 
    main.cpp
    headers/application.hpp application.cpp
    headers/mesh.hpp mesh.cpp
    headers/shader.hpp shader.cpp
    headers/image.hpp headers/image.inl image.cpp
    headers/texture.hpp texture.cpp
    headers/framebuffer.hpp framebuffer.cpp
    headers/renderbuffer.hpp renderbuffer.cpp
    headers/noisegeneration.hpp noisegeneration.cpp
    headers/camera.hpp camera.cpp
    headers/meshgeneration.hpp meshgeneration.cpp
    headers/hermite.hpp hermite.cpp
    headers/water.hpp water.cpp
    headers/skybox.hpp skybox.cpp
    headers/light.hpp
)

target_link_libraries(main PRIVATE glad::glad glfw glm::glm imgui::imgui)
target_compile_features(main PRIVATE cxx_std_20)
set_target_properties(main PROPERTIES CXX_EXTENSIONS OFF)
target_include_directories(main PRIVATE ${STB_INCLUDE_DIRS})

if (MSVC)
    target_compile_options(main PRIVATE /W3)
else()
    target_compile_options(main PRIVATE -Wall -Wextra -Wpedantic)
endif()

# Copy 'assets' directory to 'build' directory after build
add_custom_command(TARGET main POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E make_directory $<TARGET_FILE_DIR:main>/assets
    COMMAND ${CMAKE_COMMAND} -E copy_directory
    ${CMAKE_SOURCE_DIR}/assets
    $<TARGET_FILE_DIR:main>/assets
)
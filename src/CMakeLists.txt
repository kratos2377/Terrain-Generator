file(GLOB SOURCES *.cpp)
file(GLOB HEADERS *.hpp)
file(GLOB HEADERS headers/*.hpp)

add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})
target_link_libraries(${PROJECT_NAME} 
    glad
    glfw
    glm
    imgui
)
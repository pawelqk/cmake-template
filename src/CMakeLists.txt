project("${CMAKE_PROJECT_NAME}")

file(GLOB S_SRCS "*.cpp")
file(GLOB S_HEADERS "*.hpp")

add_executable(${PROJECT_NAME} ${S_SRCS} ${S_HEADERS})

set(Boost_USE_STATIC_LIBS OFF)
set(Boost_USE_MULTITHREADED ON)
set(Boost_USE_STATIC_RUNTIME OFF)
find_package(Boost 1.75.0)

include_directories(
    "${SRC_DIR}"
)

add_test(NAME ${PROJECT_NAME}
         COMMAND ${PROJECT_NAME})

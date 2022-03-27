# (1) Build a library with my application sources
set(APP_LIB_SOURCE
    code.cpp
#    Foo.cpp
#    Bar.cpp
)

add_library(${APP_LIB_NAME} ${APP_LIB_SOURCE})

# (2) Add main(..) to the application library to have something we can run
add_executable(${PROJECT} main.cpp)
target_link_libraries(${PROJECT} ${APP_LIB_NAME})
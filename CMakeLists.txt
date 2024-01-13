cmake_minimum_required(VERSION 3.27)
project(sqlite3 VERSION 3.44.2 LANGUAGES C CXX)

include(CTest)
enable_testing()

set(SQLITE_SRC src/sqlite3.c src/shell.c)

include_directories(include)
add_library(sqlite3 SHARED ${SQLITE_SRC})

install(TARGETS sqlite3 DESTINATION lib)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

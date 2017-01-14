project(utils)

set(CMAKE_C_FLAGS "-fPIC -DNDEBUG -O2 -D_FORTIFY_SOURCE=2 -fvisibility=default")
set(CMAKE_CXX_FLAGS "-fPIC -DNDEBUG -O2 -D_FORTIFY_SOURCE=2 -fvisibility=default")

aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} LIBUTILS_SRCS)

include_directories(${utils_SOURCE_DIR}/include)

add_library(utils
	SHARED
    ${LIBUTILS_SRCS}
    )

target_link_libraries(utils log)

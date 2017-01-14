project(utils)

set(CMAKE_C_FLAGS "-fPIC -DNDEBUG -O2 -D_FORTIFY_SOURCE=2 -fvisibility=default")
set(CMAKE_CXX_FLAGS "-fPIC -DNDEBUG -O2 -D_FORTIFY_SOURCE=2 -fvisibility=default")

aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} LIBUTILS_SRCS)

include_directories(${utils_SOURCE_DIR}/include)

add_library(utils
	STATIC
	${LIBUTILS_SRCS}
	)

target_link_libraries(utils log)

install(TARGETS utils ARCHIVE DESTINATION lib)
install(DIRECTORY ${utils_SOURCE_DIR}/include/utils DESTINATION include)

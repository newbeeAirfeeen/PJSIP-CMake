file(GLOB PJNATH_SRC ../src/pjnath/*.c ../include/pjnath/*.h)

add_library(pjnath OBJECT ${PJNATH_SRC})
add_library(nat STATIC ${PJNATH_SRC})
target_include_directories(nat PUBLIC ${PROJECT_SOURCE_DIR}/pjnath/include)


if(ENABLE_EXAMPLE)
    add_executable(nat_client client_main.c)
    target_link_libraries(nat_client nat pjlib-util-standard-alone pjlib-standard-alone)
endif()

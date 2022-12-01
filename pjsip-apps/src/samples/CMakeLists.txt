add_executable(ice_demo icedemo.c)
target_link_libraries(ice_demo nat pjlib-util-standard-alone pjlib-standard-alone)
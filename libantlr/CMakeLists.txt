file( GLOB SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp )
include_directories( ${CMAKE_CURRENT_SOURCE_DIR} )
add_library( cecantlr STATIC ${SRCS})
set_target_properties( cecantlr PROPERTIES COMPILE_FLAGS -fPIC )

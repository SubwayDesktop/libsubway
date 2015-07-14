project(LibSubway)
cmake_minimum_required(VERSION 2.6)
set( QT_USE_QTDBUS 1 )
find_package(Qt4 REQUIRED)

include_directories(${QT_INCLUDES} ${CMAKE_CURRENT_BINARY_DIR})

set(subway_SRCS xfitman.cpp)
qt4_automoc(${subway_SRCS})
add_library(subway SHARED ${subway_SRCS})
target_link_libraries(subway ${QT_QTCORE_LIBRARY} ${QT_QTGUI_LIBRARY} ${QT_QTDBUS_LIBRARY})
install(TARGETS subway LIBRARY DESTINATION lib)
install(FILES xfitman.h DESTINATION include/libsubway)

cmake_minimum_required(VERSION 3.15)
project(novasc VERSION 3.1 LANGUAGES C)

set(HEADERS
    eph_manager.h
    novascon.h
    novas.h
    nutation.h
    solarsystem.h
)

add_library(novasc SHARED
    ${HEADERS}
    eph_manager.c
    novas.c
    novascon.c
    nutation.c
    readeph0.c
    solsys3.c
)

install(TARGETS novasc LIBRARY DESTINATION lib)
install(FILES ${HEADERS} DESTINATION include/novasc)


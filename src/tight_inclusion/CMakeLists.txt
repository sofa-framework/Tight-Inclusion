set(SOURCES
    avx.cpp
    ccd.cpp
    interval_root_finder.cpp
    interval.cpp
    logger.cpp
)

set(HEADERS
    avx.hpp
    ccd.hpp
    interval_root_finder.hpp
    interval.hpp
    logger.hpp
    timer.hpp
    types.hpp
)




source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" PREFIX "Source Files" FILES ${HEADERS} ${SOURCES})
target_sources(tight_inclusion PRIVATE ${HEADERS} ${SOURCES})
install(FILES ${HEADERS} DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}/tight_inclusion" COMPONENT headers)


################################################################################
# Subfolders
################################################################################

if(TIGHT_INCLUSION_WITH_RATIONAL)
    add_subdirectory(rational)
endif()

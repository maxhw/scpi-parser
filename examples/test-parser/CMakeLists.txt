CMAKE_MINIMUM_REQUIRED (VERSION 3.10.1)

PROJECT (test-parser)

# CURRENT DIRECTORY
SET (ProjDirPath ${CMAKE_CURRENT_SOURCE_DIR})

# add include directory
INCLUDE_DIRECTORIES (${SCPIDirPath}/inc)
INCLUDE_DIRECTORIES (${ProjDirPath}/../common/)

# set main entry source
SET (app_SRCS
    main.c
    ${ProjDirPath}/../common/scpi-def.c
)

# Add executable file
ADD_EXECUTABLE (${PROJECT_NAME}
    ${app_SRCS}
)

# Link the executable to the library.
TARGET_LINK_LIBRARIES (${PROJECT_NAME} scpi)
TARGET_LINK_LIBRARIES (${PROJECT_NAME} pthread)
TARGET_LINK_LIBRARIES (${PROJECT_NAME} m)


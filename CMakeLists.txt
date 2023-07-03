PROJECT (scpi-parser)

CMAKE_MINIMUM_REQUIRED (VERSION 3.10.1)

IF (WIN32)
    SET (ARCH_DIR win)
ELSEIF (APPLE)
    SET (ARCH_DIR macos)
ELSEIF (UNIX)
    SET (ARCH_DIR linux)
ENDIF (WIN32)

MESSAGE (STATUS "ARCH_DIR is: " ${ARCH_DIR})

#******************************************************************************#
#                              DIRECTORY
#******************************************************************************#
SET (RootDirPath ${CMAKE_SOURCE_DIR})
SET (SCPIDirPath ${CMAKE_SOURCE_DIR}/libscpi)

#******************************************************************************#
#                              SUB DIRECTORY
#******************************************************************************#
ADD_SUBDIRECTORY(libscpi)
ADD_SUBDIRECTORY(examples)


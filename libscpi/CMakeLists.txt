CMAKE_MINIMUM_REQUIRED (VERSION 3.10.1)

PROJECT (scpi)

#MESSAGE (STATUS "PROJECT_NAME               : " ${PROJECT_NAME})
#MESSAGE (STATUS "CMAKE_PROJECT_NAME         : " ${CMAKE_PROJECT_NAME})

SET (INC_DIR inc)
SET (SRC_DIR src)

#******************************************************************************#
#                              C FLAGS
#******************************************************************************#
SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Werror")
SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wextra")
SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wmissing-prototypes")
SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wimplicit")

# Setting C Flags for Debug
SET (CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -DDEBUG")
SET (CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -g3")
SET (CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -O0")
SET (CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -g")

# Setting C Flags for Release
SET (CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -DNDEBUG")
SET (CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -O3")

#******************************************************************************#
#                              C++ FLAGS
#******************************************************************************#
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror")
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wextra")
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wmissing-prototypes")
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wimplicit")

# Setting C++ Flags for Debug
SET (CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -DDEBUG")
SET (CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g3")
SET (CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -O0")
SET (CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")

# Setting C++ Flags for Release
SET (CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -DNDEBUG")
SET (CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")

#******************************************************************************#
#                              INCLUDE
#******************************************************************************#
INCLUDE_DIRECTORIES (${INC_DIR})

#******************************************************************************#
#                              SOURCE
#******************************************************************************#
SET (scpi_SRC
    ${SRC_DIR}/error.c
    ${SRC_DIR}/expression.c
    ${SRC_DIR}/fifo.c
    ${SRC_DIR}/ieee488.c
    ${SRC_DIR}/lexer.c
    ${SRC_DIR}/minimal.c
    ${SRC_DIR}/parser.c
    ${SRC_DIR}/units.c
    ${SRC_DIR}/utils.c
)

#******************************************************************************#
#                              TARGET
#******************************************************************************#
ADD_LIBRARY (scpi ${scpi_SRC})


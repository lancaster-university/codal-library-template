include("${CODAL_UTILS_LOCATION}")

RECURSIVE_FIND_DIR(INCLUDE_DIRS "./inc" "*.h")
RECURSIVE_FIND_FILE(SOURCE_FILES "./source" "*.c??")

include_directories(${INCLUDE_DIRS})

add_library(codal-library-template
    ${SOURCE_FILES}
)

target_link_libraries(
    codal-library-template
    codal-core
)

target_include_directories(codal-library-template PUBLIC ${INCLUDE_DIRS})
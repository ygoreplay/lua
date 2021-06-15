project (lua)

set (AUTO_FILES_RESULT)
AutoFiles("." "lua" "\\.(cpp|c|h)$")

add_library (lua STATIC ${AUTO_FILES_RESULT})
if (MSVC)
    target_compile_options (lua PRIVATE /TP)
endif()

if (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    target_compile_options(lua PRIVATE -x c++)
endif()
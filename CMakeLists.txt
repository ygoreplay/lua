project (lua)

set (AUTO_FILES_RESULT)
AutoFiles("." "lua" "\\.(cpp|c|h)$")

add_library (lua STATIC ${AUTO_FILES_RESULT})
if (MSVC)
    SET_PROPERTY(SOURCE ${AUTO_FILES_RESULT} PROPERTY COMPILE_FLAGS /TP)
    target_compile_options (lua PRIVATE /TP)
endif()

if (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    target_compile_options(lua PRIVATE -x c++)
endif()
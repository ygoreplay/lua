project (lua)

set (AUTO_FILES_RESULT)
AutoFiles("." "lua" "\\.(cpp|c|h)$")

add_library (lua STATIC ${AUTO_FILES_RESULT})
if (MSVC)
    target_compile_options (lua PRIVATE /TP)
endif()
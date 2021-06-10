project (lua)

set (AUTO_FILES_RESULT)
AutoFiles("." "src" "\\.(cpp|c|h)$")

add_library (lua STATIC ${AUTO_FILES_RESULT})
target_compile_options (lua PRIVATE /TP)
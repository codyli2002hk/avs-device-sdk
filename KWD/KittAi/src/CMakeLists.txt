add_definitions("-DACSDK_LOG_MODULE=kittAiKeyWordDetector")
add_library(KITTAI SHARED
    KittAiKeyWordDetector.cpp
    snowboy-detect-cxx-compat.cpp)

target_include_directories(KITTAI PUBLIC
	"${KITTAI_KEY_WORD_DETECTOR_INCLUDE_DIR}"
	"${KWD_SOURCE_DIR}/include"
	"${KITTAI_SOURCE_DIR}/include")

target_link_libraries(KITTAI KWD AVSCommon "${KITTAI_KEY_WORD_DETECTOR_LIB_PATH}" blas)

# install target
asdk_install()
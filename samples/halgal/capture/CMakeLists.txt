find_package(PkgConfig REQUIRED)
pkg_check_modules(JPEG REQUIRED IMPORTED_TARGET libjpeg)

add_executable(sample-halgal-capture capture.c)
set_target_properties(sample-halgal-capture PROPERTIES OUTPUT_NAME halgal-captureWithoutVideo)
target_link_libraries(sample-halgal-capture halgal)

add_executable(sample-halgal-captureWithVideo capture_withVideo.c)
set_target_properties(sample-halgal-captureWithVideo PROPERTIES OUTPUT_NAME halgal-capture)
target_link_libraries(sample-halgal-captureWithVideo halgal vtcapture PkgConfig::JPEG)

find_package(ZLIB REQUIRED)

add_library(quazip STATIC)

target_include_directories(quazip PUBLIC .)
target_include_directories(quazip PRIVATE quazip/quazip)
target_compile_definitions(quazip PRIVATE QUAZIP_BUILD)
target_compile_options(quazip PRIVATE -w) # Disable warnings for third-party
                                          # software

target_sources(
  quazip
  PRIVATE
  quazip/quazip/ioapi.h
  quazip/quazip/JlCompress.cpp
  quazip/quazip/JlCompress.h
  quazip/quazip/minizip_crypt.h
  quazip/quazip/qioapi.cpp
  quazip/quazip/quaadler32.cpp
  quazip/quazip/quaadler32.h
  quazip/quazip/quachecksum32.h
  quazip/quazip/quacrc32.cpp
  quazip/quazip/quacrc32.h
  quazip/quazip/quagzipfile.cpp
  quazip/quazip/quagzipfile.h
  quazip/quazip/quaziodevice.cpp
  quazip/quazip/quaziodevice.h
  quazip/quazip/quazip.cpp
  quazip/quazip/quazip.h
  quazip/quazip/quazip.pri
  quazip/quazip/quazip.pro
  quazip/quazip/quazip.sln
  quazip/quazip/quazip.vcproj
  quazip/quazip/quazip.vcxproj
  quazip/quazip/quazip.vcxproj.filters
  quazip/quazip/quazip_global.h
  quazip/quazip/quazipdir.cpp
  quazip/quazip/quazipdir.h
  quazip/quazip/quazipfile.cpp
  quazip/quazip/quazipfile.h
  quazip/quazip/quazipfileinfo.cpp
  quazip/quazip/quazipfileinfo.h
  quazip/quazip/quazipnewinfo.cpp
  quazip/quazip/quazipnewinfo.h
  quazip/quazip/run_moc.bat
  quazip/quazip/unzip.c
  quazip/quazip/unzip.h
  quazip/quazip/zip.c
  quazip/quazip/zip.h
)

target_link_libraries(quazip PUBLIC Qt5::Core ZLIB::ZLIB)

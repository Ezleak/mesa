if with_android_stub
  stub_libs = []

  foreach lib : ['backtrace', 'cutils']
    stub_libs += static_library(
      lib,
      files(lib + '_stub.cpp'),
      include_directories : inc_include,
      install : false,
    )
  endforeach

  foreach lib : ['hardware']
    stub_libs += shared_library(
      lib,
      files(lib + '_stub.cpp'),
      include_directories : inc_include,
      install : false,
    )
  endforeach

  dep_android = declare_dependency(
    link_with : stub_libs,
    dependencies : [
      dependency('log_stub.cpp'),
      dependency('sync_stub.cpp'),
      dependency('nativewindow_stub.cpp'),
    ]
  )
endif

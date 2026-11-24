project('tinyhttpd', 'cpp',
  version : '0.10.0',
  default_options : ['warning_level=3', 'cpp_std=c++17'])

cpp = meson.get_compiler('cpp')
platform_deps = []
platform_link_args = []
if host_machine.system() == 'windows'
  platform_deps += cpp.find_library('ws2_32', required : true)
elif host_machine.system() == 'linux'
  platform_link_args += ['-static']
endif

executable('tinyhttpd',
           'src/tinyhttpd.cpp',
           dependencies : platform_deps,
           link_args : platform_link_args,
           install : true)

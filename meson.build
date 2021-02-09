project(
  'stb',
  'c',
  'cpp',
  version : '0.0.1',
  license : 'Mit'
)

#use this as a patch for the offical stb repository inside of a wrap file.
#You can view an example of this wrap file on the following link: https://github.com/noah1510/redhand/blob/main/subprojects/stb.wrap

#include the folder and delcare the dependency
incdir = include_directories('.')

stb_dep = declare_dependency(
    include_directories : incdir,
    version: meson.project_version()
)

if meson.version().version_compare('>=0.54.0')
    meson.override_dependency('stb', stb_dep)
endif

project(
  'stb',
  'c',
  'cpp',
  version : '0.0.1',
  license : 'Mit'
)

#delte the stb folder if it exists
rm = find_program('rm')
run_command(rm, '-rf', 'stb')

#find the git command and clone the latest version of stb
git = find_program('git')
r = run_command(git, 'clone', 'https://github.com/nothings/stb.git')
if r.returncode() != 0
  error('git clone failed')
endif
output = r.stdout().strip()
errortxt = r.stderr().strip()

#include the folder and delcare the dependency
incdir = include_directories('stb')

stb_dep = declare_dependency(
    include_directories : incdir,
    version: meson.project_version()
)

if meson.version().version_compare('>=0.54.0')
    meson.override_dependency('stb', stb_dep)
endif

project('dwm', 'c', default_options: ['c_std=c99'])

version = '6.2'  # TODO: version parsing

sources = ['drw.c', 'util.c']

c_args = [
  '-pedantic',
  '-Wall',
  '-Wno-deprecated-declarations',
  '-Os',
  '-D_DEFAULT_SOURCE',
  '-D_BSD_SOURCE',  # TODO: portability?
  '-D_POSIX_C_SOURCE=200809L',
  '-DVERSION="@0@"'.format(version),
  '-DXINERAMA'  # TODO: optional
]

# TODO: portability
include = include_directories(['/usr/X11R6/include', '/usr/X11R6/include/freetype2'])

dependencies = [
  dependency('x11'),
  dependency('fontconfig'),
  dependency('xft'),
  dependency('xinerama'),
]

executable(
  'dwm',
  'dwm.c',
  dependencies: dependencies,
  include_directories: include,
  c_args: c_args,
  sources: sources
)

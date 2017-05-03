include_defs('//BUCKAROO_DEPS')

linux_flags = [
  '-DHAVE_STDINT_H'
]

macos_flags = []

windows_sources = [
  'src/libFLAC/windows_unicode_filenames.c',
]

cxx_library(
  name = 'flac',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', 'FLAC/**/*.h'),
    ('include', 'share/**/*.h'),
    ('src/libFLAC/include', '**/*.h'),
  ]),
  srcs = glob([
    'src/libFLAC/**/*.c',
  ],
  excludes = windows_sources),
  compiler_flags = [
    '-std=gnu99',
  ],
  preprocessor_flags = [
    '-DPACKAGE_VERSION="1.3.2"',
    '-DFLAC__HAS_OGG=1',
    '-DHAVE_LROUND',
    '-DHAVE_SYS_PARAM_H'
  ],
  platform_preprocessor_flags = [
    ('default', linux_flags),
    ('^linux.*', linux_flags),
    ('^macos.*', macos_flags)
  ],
  visibility = [
    'PUBLIC',
  ],
  deps = BUCKAROO_DEPS,
)

cxx_library(
  name = 'flac++',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', 'FLAC++/**/*.h'),
    # ('include', 'share/**/*.h'),
    # ('src/libFLAC++/include', '**/*.h'),
  ]),
  srcs = glob([
    'src/libFLAC++/**/*.cpp',
  ],
  excludes = windows_sources),
  visibility = [
    '//...',
  ],
  deps = [
    '//:flac',
  ],
)

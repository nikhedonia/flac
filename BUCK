include_defs('//BUCKAROO_DEPS')

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
    '-DPACKAGE_VERSION="1.3.2"',
    '-DFLAC__HAS_OGG=1',
    '-DHAVE_LROUND',
  ],
  visibility = [
    'PUBLIC',
  ],
  deps = BUCKAROO_DEPS,
)

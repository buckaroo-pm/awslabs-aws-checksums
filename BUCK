load('//:subdir_glob.bzl', 'subdir_glob')

arm_srcs = glob([
  'source/arm/**/*.c', 
])

intel_srcs = glob([
  'source/intel/**/*.c', 
])

windows_srcs = glob([
  'source/visualc/**/*.c', 
])

cxx_library(
  name = 'aws-checksums', 
  header_namespace = '', 
  exported_headers = subdir_glob([
    ('include', '**/*.h'), 
  ]), 
  srcs = glob([
    'source/*.c', 
  ]), 
  platform_srcs = [
    ('.*arm.*', arm_srcs), 
    ('macos.*', intel_srcs), 
    ('linux.*', intel_srcs), 
    ('windows.*', windows_srcs), 
  ], 
  visibility = [
    'PUBLIC', 
  ], 
)

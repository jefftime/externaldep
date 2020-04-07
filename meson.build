project('example', 'c')

foo_dir = meson.source_root() + '/foo'
foo = custom_target(
  'libfoo',
  input: [foo_dir + '/foo.c'],
  output: ['libfoo.a'],
  command: [
    'make',
    '-C',
    foo_dir
  ]
)
foo_dep = declare_dependency(
  link_with: foo
)

executable(
  'example',
  'src/main.c',
  dependencies: [
    foo_dep
  ]
)

project('Void',
        version: '20.04',
        meson_version: '>= 0.51',
        license : ['GPL3', 'CC BY-SA 4.0'],
        default_options: ['prefix=/usr'])


components = ['icons', 'gnome-shell', 'gtk', 'sounds', 'sessions']

common_scss_path = join_paths(meson.current_source_dir(), 'common-scss')
common_scss_deps = run_command(
  'find', common_scss_path, '-name', '_*.scss'
).stdout().strip().split('\n')

foreach component: components
  if not get_option(component)
    message('skip component ' + component)
    continue
  endif

  message('build component ' + component)
  subdir(component)

endforeach

subdir('communitheme-compat')

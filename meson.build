if get_option('use_vendored_windows_sdl')
  sdl2_dll = configure_file(
    copy: true,
    input: 'lib' / host_machine.cpu_family() / 'SDL2.dll',
    output: 'SDL2.dll',
  )

  sdl2 = declare_dependency(
    include_directories: include_directories('include'),
    link_with: static_library(
      'sdl2_libs',
      [],
      objects: [
        'lib' / host_machine.cpu_family() / 'SDL2main.lib',
        'lib' / host_machine.cpu_family() / 'SDL2.lib',
      ],
    ),
  )
else
  sdl2 = dependency('SDL2')
endif

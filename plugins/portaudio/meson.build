
portaudio_sources = [
  'portaudio.c'
]

portaudio_dep = dependency('portaudio-2.0', required: get_option('plugin-portaudio'))

has_portaudio = portaudio_dep.found()

if has_portaudio
plugin_portaudio = shared_library('portaudio', portaudio_sources,
  name_prefix: '',
  install : true,
  install_dir: plugindir,
  include_directories: deadbeef_inc,
  dependencies : [portaudio_dep, dependency('blocks'), cc.find_library('dispatch')],
)
endif

summary({'PortAudio': has_portaudio}, bool_yn: true, section: 'Plugins')

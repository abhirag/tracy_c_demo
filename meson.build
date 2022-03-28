project('tracy_c_demo', 'c', 'cpp',
  version : '0.1',
  default_options : ['warning_level=3', 
                     'c_std=c11'])
add_project_arguments(['-DTRACY_ENABLE=1', '-DTRACY_NO_EXIT=1'], language : ['c', 'cpp'])
add_project_link_arguments(['-lm','-lstdc++', '-pthread', '-ldl'], language : ['c', 'cpp'])

log_sp = subproject('log')
log = log_sp.get_variable('log_dep')

inc = include_directories('include', 'tracy')
main_src = files('src/main.c')
tracy_src = files('tracy/TracyClient.cpp')

tracy_c_demo = executable('tracy_c_demo', 
                          [main_src, tracy_src],
                          include_directories: inc,
                          dependencies: [log])







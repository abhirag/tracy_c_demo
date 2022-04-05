# Tracy C Demo

Demonstrating client setup and client markup for [Tracy Profiler](https://github.com/wolfpld/tracy) in C. Find more details [here](https://www.abhirag.com/blog/tracy/).

## Build
We are using [meson](https://mesonbuild.com/) with the [ninja](https://ninja-build.org/) backend:

| `meson`       | `ninja`       |
| ------------- | ------------- |
| 0.59.2        | 1.10.2        |

1. Get the `ninja` binary from [here](https://github.com/ninja-build/ninja/releases)
2. Add the location of your `ninja` binary to your PATH environment variable
3. [Install meson](https://mesonbuild.com/Quick-guide.html)
4. Navigate to the project directory
5. `$ meson builddir`
6. `$ cd builddir`
7. `$ meson compile`
8. The produced binary in `builddir` will send traces to the `Tracy` server

## Disable Tracy
Remove the following line from [meson.build](meson.build) to stop collecting traces:

`add_project_arguments(['-DTRACY_ENABLE=1', '-DTRACY_NO_EXIT=1'], language : ['c', 'cpp'])`



This repo describes a bug candidate that Bazel can't create coverage report on windows with msys-64/mingw-gcc

Reproduce steps
```shell
bazel coverage --compiler=mingw-gcc  //src:test_lib1  --java_runtime_version=remotejdk_11 --subcommands

D:\code\workspace\LearningProjects\BazelLearn>bazel coverage --compiler=mingw-gcc  //src:test_lib1  --java_runtime_version=remotejdk_11 --subcommands
INFO: Using default value for --instrumentation_filter: "^//src[/:]".
INFO: Override the above default with --instrumentation_filter
INFO: Analyzed target //src:test_lib1 (49 packages loaded, 942 targets configured).
INFO: Found 1 test target...
SUBCOMMAND: # @bazel_tools//tools/jdk:platformclasspath [action 'JavaToolchainCompileClasses external/bazel_tools/tools/jdk/platformclasspath_classes [for host]', configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
external\remotejdk11_win\bin\javac -source 8 -target 8 -Xlint:-options -cp external/remotejdk11_win/lib/tools.jar -d bazel-out/host/bin/external/bazel_tools/tools/jdk/platformclasspath_classes external/bazel_tools/tools/jdk/DumpPlatformClassPath.java
# Configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googlemock/src/gmock-cardinalities.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-cardinalities.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-cardinalities.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock-cardinalities.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-cardinalities.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googlemock/src/gmock-matchers.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-matchers.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-matchers.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock-matchers.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-matchers.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:lib1 [action 'Compiling src/lib1.cpp', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/src/_objs/lib1/lib1.d -frandom-seed=bazel-out/x64_windows-dbg/bin/src/_objs/lib1/lib1.o -iquote . -iquote bazel-out/x64_windows-dbg/bin -fprofile-arcs -ftest-coverage -g -Og -c src/lib1.cpp -o bazel-out/x64_windows-dbg/bin/src/_objs/lib1/lib1.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-death-test.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-death-test.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-death-test.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-death-test.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-death-test.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-printers.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-printers.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-printers.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-printers.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-printers.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:test_lib1 [action 'Compiling src/test.cpp', configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/src/_objs/test_lib1/test.d -frandom-seed=bazel-out/x64_windows-dbg/bin/src/_objs/test_lib1/test.o -iquote . -iquote bazel-out/x64_windows-dbg/bin -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -iquote external/bazel_tools -iquote bazel-out/x64_windows-dbg/bin/external/bazel_tools -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -fprofile-arcs -ftest-coverage -g -Og -c src/test.cpp -o bazel-out/x64_windows-dbg/bin/src/_objs/test_lib1/test.o
# Configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest_main [action 'Compiling googlemock/src/gmock_main.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest_main/gmock_main.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest_main/gmock_main.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock_main.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest_main/gmock_main.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-filepath.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-filepath.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-filepath.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-filepath.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-filepath.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-matchers.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-matchers.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-matchers.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-matchers.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-matchers.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-port.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-port.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-port.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-port.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-port.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googlemock/src/gmock-internal-utils.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-internal-utils.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-internal-utils.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock-internal-utils.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-internal-utils.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-typed-test.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-typed-test.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-typed-test.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-typed-test.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-typed-test.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googletest/src/gtest-test-part.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-test-part.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-test-part.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googletest/src/gtest-test-part.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-test-part.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googlemock/src/gmock.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Compiling googlemock/src/gmock-spec-builders.cc', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -std=gnu++0x -MD -MF bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-spec-builders.d -frandom-seed=bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-spec-builders.o -iquote external/googletest -iquote bazel-out/x64_windows-dbg/bin/external/googletest -isystem external/googletest/googlemock -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock -isystem external/googletest/googlemock/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googlemock/include -isystem external/googletest/googletest -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest -isystem external/googletest/googletest/include -isystem bazel-out/x64_windows-dbg/bin/external/googletest/googletest/include -g -Og -c external/googletest/googlemock/src/gmock-spec-builders.cc -o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-spec-builders.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:lib1 [action 'Linking src/liblib1.a', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\ar rcsD bazel-out/x64_windows-dbg/bin/src/liblib1.a bazel-out/x64_windows-dbg/bin/src/_objs/lib1/lib1.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @bazel_tools//tools/jdk:platformclasspath [action 'JavaToolchainCompileBootClasspath external/bazel_tools/tools/jdk/platformclasspath.jar [for host]', configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
external\remotejdk11_win\bin\java.exe -XX:+IgnoreUnrecognizedVMOptions --add-exports=jdk.compiler/com.sun.tools.javac.api=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.platform=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED -cp bazel-out/host/bin/external/bazel_tools/tools/jdk/platformclasspath_classes;external/remotejdk11_win/lib/tools.jar DumpPlatformClassPath bazel-out/host/bin/external/bazel_tools/tools/jdk/platformclasspath.jar external/remotejdk11_win
# Configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest_main [action 'Linking external/googletest/libgtest_main.a', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\ar rcsD bazel-out/x64_windows-dbg/bin/external/googletest/libgtest_main.a bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest_main/gmock_main.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @bazel_tools//tools/jdk:platformclasspath [action 'JavaToolchainCompileClasses external/bazel_tools/tools/jdk/platformclasspath_classes', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
external\remotejdk11_win\bin\javac -source 8 -target 8 -Xlint:-options -cp external/remotejdk11_win/lib/tools.jar -d bazel-out/x64_windows-dbg/bin/external/bazel_tools/tools/jdk/platformclasspath_classes external/bazel_tools/tools/jdk/DumpPlatformClassPath.java
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @bazel_tools//tools/jdk:platformclasspath [action 'JavaToolchainCompileBootClasspath external/bazel_tools/tools/jdk/platformclasspath.jar', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
external\remotejdk11_win\bin\java.exe -XX:+IgnoreUnrecognizedVMOptions --add-exports=jdk.compiler/com.sun.tools.javac.api=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.platform=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED -cp bazel-out/x64_windows-dbg/bin/external/bazel_tools/tools/jdk/platformclasspath_classes;external/remotejdk11_win/lib/tools.jar DumpPlatformClassPath bazel-out/x64_windows-dbg/bin/external/bazel_tools/tools/jdk/platformclasspath.jar external/remotejdk11_win
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @remote_coverage_tools//:Main [action 'Building external/remote_coverage_tools/Main.jar () [for host]', configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET LC_CTYPE=en_US.UTF-8
    SET PATH=C:\msys64\usr\bin;C:\msys64\bin;C:\WINDOWS;C:\WINDOWS\System32;C:\WINDOWS\System32\WindowsPowerShell\v1.0;C:\Program Files (x86)\VMware\VMware Workstation\bin\;C:\Python38\Scripts;C:\Python38;C:\Users\xxx\AppData\Roaming\ActiveState\bin;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\libnvvp;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;c:\Program Files\TortoiseSVN\bin;C:\EC-Apps\EDIABAS\BIN;C:\NASM;C:\OpenSSL-Win64\bin;D:\installer\mingw64_posix\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin\;D:\code\workspace\github\wabt\build_win\DEBUG;D:\code\workspace\github\binaryen\build_win\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\Wireshark;C:\Program Files\nodejs\;C:\Program Files\CMake\bin;C:\Program Files (x86)\Microsoft SQL Server\150\DTS\Binn\;C:\Program Files\Azure Data Studio\bin;C:\softwares\jom;D:\avro_x86\bin;D:\boost_msvc_dll\lib;D:\avro_x86\lib;D:\code\workspace\github\snappy-visual-cpp\x64\Debug;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;D:\Qt6_x86\bin;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;C:\Perl64\bin;D:\openssl_x86\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Nmap;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.31.31103\bin\Hostx86\x64;C:\Program Files\doxygen\bin;C:\Program Files\Graphviz\bin;C:\Program Files\PuTTY\;C:\Program Files\bazel;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\Program Files (x86)\Java\jre1.8.0_341\bin;C:\workspace\gpp\gpp\Debug;D:\Qt6_x86_release\bin;D:\avro_x86_release\lib;D:\boost_msvc_dll_release\lib;C:\Program Files\Go\bin;C:\Program Files\CenterTools\DriveLock\;C:\PROGRA~1\IBM\SQLLIB\BIN;C:\PROGRA~1\IBM\SQLLIB\FUNCTION;C:\Program Files\dotnet\;C:\Python38\Scripts\;C:\Python38\;C:\Ruby27-x64\bin;C:\Users\xxx\AppData\Local\Microsoft\WindowsApps;C:\Users\xxx\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\xxx\.dotnet\tools;C:\Users\xxx\AppData\Roaming\npm;C:\Users\xxx\AppData\Local\Programs\Git\cmd;C:\Users\xxx\go\bin
    SET RUNFILES_MANIFEST_ONLY=1
  external\remotejdk11_win\bin\java.exe -XX:-CompactStrings --add-exports=jdk.compiler/com.sun.tools.javac.api=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.main=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.model=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.parser=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.processing=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.resources=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.tree=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.code=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.comp=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.file=ALL-UNNAMED --add-opens=java.base/java.nio=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --patch-module=java.compiler=external/remote_java_tools/java_tools/java_compiler.jar --patch-module=jdk.compiler=external/remote_java_tools/java_tools/jdk_compiler.jar -jar external/remote_java_tools/java_tools/JavaBuilder_deploy.jar @bazel-out/host/bin/external/remote_coverage_tools/Main.jar-0.params @bazel-out/host/bin/external/remote_coverage_tools/Main.jar-1.params
# Configuration: 018ac01164ebf7b3c0ac75cfde8dec421a49332ca877c942eb5a2adae5a1e82a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @remote_coverage_tools//:Main [action 'Building external/remote_coverage_tools/Main.jar ()', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET LC_CTYPE=en_US.UTF-8
    SET PATH=C:\msys64\usr\bin;C:\msys64\bin;C:\WINDOWS;C:\WINDOWS\System32;C:\WINDOWS\System32\WindowsPowerShell\v1.0;C:\Program Files (x86)\VMware\VMware Workstation\bin\;C:\Python38\Scripts;C:\Python38;C:\Users\xxx\AppData\Roaming\ActiveState\bin;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\libnvvp;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;c:\Program Files\TortoiseSVN\bin;C:\EC-Apps\EDIABAS\BIN;C:\NASM;C:\OpenSSL-Win64\bin;D:\installer\mingw64_posix\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin\;D:\code\workspace\github\wabt\build_win\DEBUG;D:\code\workspace\github\binaryen\build_win\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\Wireshark;C:\Program Files\nodejs\;C:\Program Files\CMake\bin;C:\Program Files (x86)\Microsoft SQL Server\150\DTS\Binn\;C:\Program Files\Azure Data Studio\bin;C:\softwares\jom;D:\avro_x86\bin;D:\boost_msvc_dll\lib;D:\avro_x86\lib;D:\code\workspace\github\snappy-visual-cpp\x64\Debug;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;D:\Qt6_x86\bin;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;C:\Perl64\bin;D:\openssl_x86\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Nmap;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.31.31103\bin\Hostx86\x64;C:\Program Files\doxygen\bin;C:\Program Files\Graphviz\bin;C:\Program Files\PuTTY\;C:\Program Files\bazel;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\Program Files (x86)\Java\jre1.8.0_341\bin;C:\workspace\gpp\gpp\Debug;D:\Qt6_x86_release\bin;D:\avro_x86_release\lib;D:\boost_msvc_dll_release\lib;C:\Program Files\Go\bin;C:\Program Files\CenterTools\DriveLock\;C:\PROGRA~1\IBM\SQLLIB\BIN;C:\PROGRA~1\IBM\SQLLIB\FUNCTION;C:\Program Files\dotnet\;C:\Python38\Scripts\;C:\Python38\;C:\Ruby27-x64\bin;C:\Users\xxx\AppData\Local\Microsoft\WindowsApps;C:\Users\xxx\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\xxx\.dotnet\tools;C:\Users\xxx\AppData\Roaming\npm;C:\Users\xxx\AppData\Local\Programs\Git\cmd;C:\Users\xxx\go\bin
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  external\remotejdk11_win\bin\java.exe -XX:-CompactStrings --add-exports=jdk.compiler/com.sun.tools.javac.api=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.main=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.model=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.parser=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.processing=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.resources=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.tree=ALL-UNNAMED --add-exports=jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.code=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.comp=ALL-UNNAMED --add-opens=jdk.compiler/com.sun.tools.javac.file=ALL-UNNAMED --add-opens=java.base/java.nio=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --patch-module=java.compiler=external/remote_java_tools/java_tools/java_compiler.jar --patch-module=jdk.compiler=external/remote_java_tools/java_tools/jdk_compiler.jar -jar external/remote_java_tools/java_tools/JavaBuilder_deploy.jar @bazel-out/x64_windows-dbg/bin/external/remote_coverage_tools/Main.jar-0.params @bazel-out/x64_windows-dbg/bin/external/remote_coverage_tools/Main.jar-1.params
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # @googletest//:gtest [action 'Linking external/googletest/libgtest.a', configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\ar rcsD bazel-out/x64_windows-dbg/bin/external/googletest/libgtest.a bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-cardinalities.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-internal-utils.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-matchers.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock-spec-builders.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gmock.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-death-test.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-filepath.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-matchers.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-port.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-printers.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-test-part.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest-typed-test.o bazel-out/x64_windows-dbg/bin/external/googletest/_objs/gtest/gtest.o
# Configuration: 4fad009d6f326d2fc8ab43d3cbc8857635ed00263c03787524e35ce70bee3d16
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:test_lib1 [action 'Linking src/test_lib1.exe', configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET PATH=c:/msys64/mingw64/bin
    SET PWD=/proc/self/cwd
    SET RUNFILES_MANIFEST_ONLY=1
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
  c:\msys64\mingw64\bin\gcc -o bazel-out/x64_windows-dbg/bin/src/test_lib1.exe bazel-out/x64_windows-dbg/bin/src/_objs/test_lib1/test.o bazel-out/x64_windows-dbg/bin/external/googletest/libgtest_main.a bazel-out/x64_windows-dbg/bin/external/googletest/libgtest.a bazel-out/x64_windows-dbg/bin/src/liblib1.a --coverage -lstdc++
# Configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:test_lib1 [action 'Testing //src:test_lib1', configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET BAZEL_CC_COVERAGE_TOOL=GCOV
    SET CC_CODE_COVERAGE_SCRIPT=external/bazel_tools/tools/test/collect_cc_coverage.sh
    SET COVERAGE_DIR=_coverage/src/test_lib1/test
    SET COVERAGE_GCOV_PATH=c:/msys64/mingw64/bin/gcov
    SET COVERAGE_MANIFEST=bazel-out/x64_windows-dbg/bin/src/test_lib1.instrumented_files
    SET COVERAGE_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/coverage.dat
    SET EXPERIMENTAL_SPLIT_XML_GENERATION=1
    SET GENERATE_LLVM_LCOV=0
    SET IS_COVERAGE_SPAWN=0
    SET JAVA_RUNFILES=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET LCOV_MERGER=bazel-out/x64_windows-dbg/bin/external/remote_coverage_tools/Main.exe
    SET LLVM_COV=
    SET PATH=C:\msys64\usr\bin;C:\msys64\bin;C:\WINDOWS;C:\WINDOWS\System32;C:\WINDOWS\System32\WindowsPowerShell\v1.0;C:\Program Files (x86)\VMware\VMware Workstation\bin\;C:\Python38\Scripts;C:\Python38;C:\Users\xxx\AppData\Roaming\ActiveState\bin;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\libnvvp;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;c:\Program Files\TortoiseSVN\bin;C:\EC-Apps\EDIABAS\BIN;C:\NASM;C:\OpenSSL-Win64\bin;D:\installer\mingw64_posix\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin\;D:\code\workspace\github\wabt\build_win\DEBUG;D:\code\workspace\github\binaryen\build_win\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\Wireshark;C:\Program Files\nodejs\;C:\Program Files\CMake\bin;C:\Program Files (x86)\Microsoft SQL Server\150\DTS\Binn\;C:\Program Files\Azure Data Studio\bin;C:\softwares\jom;D:\avro_x86\bin;D:\boost_msvc_dll\lib;D:\avro_x86\lib;D:\code\workspace\github\snappy-visual-cpp\x64\Debug;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;D:\Qt6_x86\bin;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;C:\Perl64\bin;D:\openssl_x86\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Nmap;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.31.31103\bin\Hostx86\x64;C:\Program Files\doxygen\bin;C:\Program Files\Graphviz\bin;C:\Program Files\PuTTY\;C:\Program Files\bazel;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\Program Files (x86)\Java\jre1.8.0_341\bin;C:\workspace\gpp\gpp\Debug;D:\Qt6_x86_release\bin;D:\avro_x86_release\lib;D:\boost_msvc_dll_release\lib;C:\Program Files\Go\bin;C:\Program Files\CenterTools\DriveLock\;C:\PROGRA~1\IBM\SQLLIB\BIN;C:\PROGRA~1\IBM\SQLLIB\FUNCTION;C:\Program Files\dotnet\;C:\Python38\Scripts\;C:\Python38\;C:\Ruby27-x64\bin;C:\Users\xxx\AppData\Local\Microsoft\WindowsApps;C:\Users\xxx\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\xxx\.dotnet\tools;C:\Users\xxx\AppData\Roaming\npm;C:\Users\xxx\AppData\Local\Programs\Git\cmd;C:\Users\xxx\go\bin
    SET PYTHON_RUNFILES=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET RUNFILES_DIR=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET RUNFILES_MANIFEST_ONLY=1
    SET RUNTEST_PRESERVE_CWD=1
    SET RUN_UNDER_RUNFILES=1
    SET SPLIT_COVERAGE_POST_PROCESSING=0
    SET TEST_BINARY=src/test_lib1.exe
    SET TEST_INFRASTRUCTURE_FAILURE_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.infrastructure_failure
    SET TEST_LOGSPLITTER_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.raw_splitlogs/test.splitlogs
    SET TEST_PREMATURE_EXIT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.exited_prematurely
    SET TEST_SIZE=small
    SET TEST_SRCDIR=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET TEST_TARGET=//src:test_lib1
    SET TEST_TIMEOUT=300
    SET TEST_TMPDIR=_tmp/cb5abaaa0ba00e71f730c7771e33acf3
    SET TEST_UNDECLARED_OUTPUTS_ANNOTATIONS=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest/ANNOTATIONS
    SET TEST_UNDECLARED_OUTPUTS_ANNOTATIONS_DIR=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest
    SET TEST_UNDECLARED_OUTPUTS_DIR=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs
    SET TEST_UNDECLARED_OUTPUTS_MANIFEST=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest/MANIFEST
    SET TEST_UNDECLARED_OUTPUTS_ZIP=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs/outputs.zip
    SET TEST_UNUSED_RUNFILES_LOG_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.unused_runfiles_log
    SET TEST_WARNINGS_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.warnings
    SET TEST_WORKSPACE=__main__
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
    SET TZ=UTC
    SET XML_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.xml
  external\bazel_tools\tools\test\tw.exe external/bazel_tools/tools/test/collect_coverage.sh src/test_lib1.exe
# Configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a
# Execution platform: @local_config_platform//:host
SUBCOMMAND: # //src:test_lib1 [action 'Testing //src:test_lib1', configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a, execution platform: @local_config_platform//:host]
cd /d C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__
  SET BAZEL_CC_COVERAGE_TOOL=GCOV
    SET CC_CODE_COVERAGE_SCRIPT=external/bazel_tools/tools/test/collect_cc_coverage.sh
    SET COVERAGE_DIR=_coverage/src/test_lib1/test
    SET COVERAGE_GCOV_PATH=c:/msys64/mingw64/bin/gcov
    SET COVERAGE_MANIFEST=bazel-out/x64_windows-dbg/bin/src/test_lib1.instrumented_files
    SET COVERAGE_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/coverage.dat
    SET EXPERIMENTAL_SPLIT_XML_GENERATION=1
    SET GENERATE_LLVM_LCOV=0
    SET IS_COVERAGE_SPAWN=0
    SET JAVA_RUNFILES=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET LCOV_MERGER=bazel-out/x64_windows-dbg/bin/external/remote_coverage_tools/Main.exe
    SET LLVM_COV=
    SET PATH=C:\msys64\usr\bin;C:\msys64\bin;C:\WINDOWS;C:\WINDOWS\System32;C:\WINDOWS\System32\WindowsPowerShell\v1.0;C:\Program Files (x86)\VMware\VMware Workstation\bin\;C:\Python38\Scripts;C:\Python38;C:\Users\xxx\AppData\Roaming\ActiveState\bin;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\libnvvp;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;c:\Program Files\TortoiseSVN\bin;C:\EC-Apps\EDIABAS\BIN;C:\NASM;C:\OpenSSL-Win64\bin;D:\installer\mingw64_posix\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin\;D:\code\workspace\github\wabt\build_win\DEBUG;D:\code\workspace\github\binaryen\build_win\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\Wireshark;C:\Program Files\nodejs\;C:\Program Files\CMake\bin;C:\Program Files (x86)\Microsoft SQL Server\150\DTS\Binn\;C:\Program Files\Azure Data Studio\bin;C:\softwares\jom;D:\avro_x86\bin;D:\boost_msvc_dll\lib;D:\avro_x86\lib;D:\code\workspace\github\snappy-visual-cpp\x64\Debug;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;D:\Qt6_x86\bin;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;C:\Perl64\bin;D:\openssl_x86\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Nmap;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.31.31103\bin\Hostx86\x64;C:\Program Files\doxygen\bin;C:\Program Files\Graphviz\bin;C:\Program Files\PuTTY\;C:\Program Files\bazel;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\softwares\Tasking\ctc\bin;C:\Program Files\ninja;C:\softwares\Tasking\bin;C:\workspace\cdc2\Tools\CDC_Signature_Tool;C:\Program Files (x86)\Java\jre1.8.0_341\bin;C:\workspace\gpp\gpp\Debug;D:\Qt6_x86_release\bin;D:\avro_x86_release\lib;D:\boost_msvc_dll_release\lib;C:\Program Files\Go\bin;C:\Program Files\CenterTools\DriveLock\;C:\PROGRA~1\IBM\SQLLIB\BIN;C:\PROGRA~1\IBM\SQLLIB\FUNCTION;C:\Program Files\dotnet\;C:\Python38\Scripts\;C:\Python38\;C:\Ruby27-x64\bin;C:\Users\xxx\AppData\Local\Microsoft\WindowsApps;C:\Users\xxx\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\xxx\.dotnet\tools;C:\Users\xxx\AppData\Roaming\npm;C:\Users\xxx\AppData\Local\Programs\Git\cmd;C:\Users\xxx\go\bin
    SET PYTHON_RUNFILES=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET RUNFILES_DIR=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET RUNFILES_MANIFEST_ONLY=1
    SET RUNTEST_PRESERVE_CWD=1
    SET RUN_UNDER_RUNFILES=1
    SET SPLIT_COVERAGE_POST_PROCESSING=0
    SET TEST_BINARY=src/test_lib1.exe
    SET TEST_INFRASTRUCTURE_FAILURE_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.infrastructure_failure
    SET TEST_LOGSPLITTER_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.raw_splitlogs/test.splitlogs
    SET TEST_NAME=//src:test_lib1
    SET TEST_PREMATURE_EXIT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.exited_prematurely
    SET TEST_SHARD_INDEX=0
    SET TEST_SIZE=small
    SET TEST_SRCDIR=bazel-out/x64_windows-dbg/bin/src/test_lib1.exe.runfiles
    SET TEST_TARGET=//src:test_lib1
    SET TEST_TIMEOUT=300
    SET TEST_TMPDIR=_tmp/cb5abaaa0ba00e71f730c7771e33acf3
    SET TEST_TOTAL_SHARDS=0
    SET TEST_UNDECLARED_OUTPUTS_ANNOTATIONS=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest/ANNOTATIONS
    SET TEST_UNDECLARED_OUTPUTS_ANNOTATIONS_DIR=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest
    SET TEST_UNDECLARED_OUTPUTS_DIR=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs
    SET TEST_UNDECLARED_OUTPUTS_MANIFEST=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs_manifest/MANIFEST
    SET TEST_UNDECLARED_OUTPUTS_ZIP=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.outputs/outputs.zip
    SET TEST_UNUSED_RUNFILES_LOG_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.unused_runfiles_log
    SET TEST_WARNINGS_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.warnings
    SET TEST_WORKSPACE=__main__
    SET TSK_LICENSE_KEY_SW260800=a826-9d74-a0d1-d4ad
    SET TSK_LICENSE_SERVER=wlic01s1.muc:1890
    SET TZ=UTC
    SET XML_OUTPUT_FILE=bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.xml
  external\bazel_tools\tools\test\xml.exe bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.log bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.xml 0 1
# Configuration: ff03d927aa9358bfbda0b430dae58a002109a7154e9c0ec1f822bc0576997f5a
# Execution platform: @local_config_platform//:host
FAIL: //src:test_lib1 (see C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__/bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.log)
ERROR: D:/code/workspace/learningprojects/bazellearn/src/BUILD:17:8: output 'src/test_lib1/coverage.dat' was not created
ERROR: D:/code/workspace/learningprojects/bazellearn/src/BUILD:17:8: Testing //src:test_lib1 failed: not all outputs were created or valid
Target //src:test_lib1 up-to-date:
  bazel-bin/src/test_lib1.exe
INFO: Elapsed time: 15.501s, Critical Path: 14.72s
INFO: 39 processes: 11 internal, 26 local, 2 worker.
FAILED: Build did NOT complete successfully
//src:test_lib1                                                          FAILED in 0.1s
  C:/users/xxx/_bazel_xxx/yl5maq7v/execroot/__main__/bazel-out/x64_windows-dbg/testlogs/src/test_lib1/test.log

FAILED: Build did NOT complete successfully

```

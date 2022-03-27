# Build
```
mkdir build ; cd build
cmake -DCOMPILE_TESTS=OFF ../
make -j4
```
Result
```
[ 25%] Building CXX object src/CMakeFiles/fooAppLib.dir/code.cpp.o
[ 50%] Linking CXX static library libfooAppLib.a
[ 50%] Built target fooAppLib
[ 75%] Building CXX object src/CMakeFiles/fooApp.dir/main.cpp.o
[100%] Linking CXX executable fooApp
[100%] Built target fooApp
```

# With test option
```
mkdir build ; cd build
cmake -DCOMPILE_TESTS=ON ../
make -j4
```
Result:
```
[ 14%] Building CXX object src/CMakeFiles/fooAppLib.dir/code.cpp.o
[ 28%] Linking CXX static library libfooAppLib.a
[ 28%] Built target fooAppLib
[ 71%] Building CXX object tests/CMakeFiles/fooApp_tests.dir/main.cpp.o
[ 71%] Building CXX object src/CMakeFiles/fooApp.dir/main.cpp.o
[ 71%] Building CXX object tests/CMakeFiles/fooApp_tests.dir/codeTest.cpp.o
[ 85%] Linking CXX executable fooApp
[ 85%] Built target fooApp
[100%] Linking CXX executable fooApp_tests
.
OK (1 tests, 1 ran, 1 checks, 0 ignored, 0 filtered out, 0 ms)
```
# Run with Ctest
```
ctest -V
make test
```
Result:
```
vuson@sckt:~/cmake_cpputest/build$ ctest -V
UpdateCTestConfiguration  from :/home/vuson/cmake_cpputest/build/DartConfiguration.tcl
UpdateCTestConfiguration  from :/home/vuson/cmake_cpputest/build/DartConfiguration.tcl
Test project /home/vuson/cmake_cpputest/build
Constructing a list of tests
Done constructing a list of tests
Updating test list for fixtures
Added 0 tests to meet fixture requirements
Checking test dependency graph...
Checking test dependency graph end
test 1
    Start 1: fooApp_tests

1: Test command: /home/vuson/cmake_cpputest/build/tests/fooApp_tests
1: Test timeout computed to be: 10000000
1: .
1: OK (1 tests, 1 ran, 1 checks, 0 ignored, 0 filtered out, 0 ms)
1: 
1/1 Test #1: fooApp_tests .....................   Passed    0.01 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.02 sec
```

# Tutorial ref
https://r4nd0m6uy.ch/cmake-and-cpputest.html
https://www.sparkpost.com/blog/getting-started-cpputest/
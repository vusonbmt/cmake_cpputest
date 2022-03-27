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

# Tutorial ref
https://r4nd0m6uy.ch/cmake-and-cpputest.html
https://www.sparkpost.com/blog/getting-started-cpputest/
**AIX compilation using open-xl**
```bash
ulimit -m unlimited

ulimit -d unlimited

ulimit -f unlimited

export OBJECT_MODE=64

export CC="/opt/IBM/openxlC/17.1.2/bin/ibm-clang  -pthread -m64  " 

export CXX="/opt/IBM/openxlC/17.1.2/bin/ibm-clang++_r  -pthread -m64"

export CFLAGS="-mcmodel=large"

export CXXFLAGS="-mcmodel=large"

cmake . -B build \
	-DBUILD_opencv_python3=OFF \
	-DBUILD_opencv_python2=OFF \
	-DBUILD_SHARED_LIBS=ON \
	-DOPENCV_SKIP_GC_SECTIONS=ON \
	-DCMAKE_INSTALL_PREFIX=/usr/local

cmake --build build -j 4

cmake  --install build
```

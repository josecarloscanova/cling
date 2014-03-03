          _  _  _      _         _  _  _   _           _      _  _  _
       _ (_)(_)(_) _  (_)       (_)(_)(_) (_) _       (_)  _ (_)(_)(_) _
      (_)         (_) (_)          (_)    (_)(_)_     (_) (_)         (_)
      (_)             (_)          (_)    (_)  (_)_   (_) (_)    _  _  _
      (_)             (_)          (_)    (_)    (_)_ (_) (_)   (_)(_)(_)
      (_)          _  (_)          (_)    (_)      (_)(_) (_)         (_)
      (_) _  _  _ (_) (_) _  _   _ (_) _  (_)         (_) (_) _  _  _ (_)
         (_)(_)(_)    (_)(_)(_) (_)(_)(_) (_)         (_)    (_)(_)(_)(_)

--------------------------------------------------------------------------------

1. INSTALLATION 

--------------------------------------------------------------------------------
1.1. Binaries
   We offer binary snapshots for download at https://ecsft.cern.ch/dist/cling
--------------------------------------------------------------------------------
1.2 Source

   CLING source depends on the LLVM[1] and CLANG[2] headers and libraries.
You will also need CMake[3] >= 2.6.1 or GNU Make to build all of those
packages and subversion[4] and git[5] to get the source code.

   [1] http://llvm.org
   [2] http://clang.llvm.org
   [3] http://cmake.org
   [4] http://subversion.tigris.org
   [5] http://git-scm.com

1.2.1 Building

   Building LLVM and CLANG you must:

   * Check out the sources:

      git clone http://root.cern.ch/git/llvm.git src
      cd src
      git checkout cling-patches
      cd tools
      git clone http://root.cern.ch/git/cling.git
      git clone http://root.cern.ch/git/clang.git
      cd clang
      git checkout cling-patches

   * Configure, build and install them, either using CMake:

     cd ..
     mkdir build
     cd build
     cmake -DCMAKE_INSTALL_PREFIX=/some/install/dir \
           -DLLVM_TARGETS_TO_BUILD=CBackend\;CppBackend\;X86 \
           -DCMAKE_BUILD_TYPE=Debug \
           ../src
     make
     make install

     or GNU Make (see ../src/configure --help for all options):

     cd ..
     mkdir build
     cd build
     ../src/configure --prefix=/some/install/dir
     make
     make install
--------------------------------------------------------------------------------

2. USAGE

   To get started run: /some/install/dir/bin/cling --help
   or type
   /some/install/dir/bin/cling
   [cling]$ .help
--------------------------------------------------------------------------------
3. Developers' corner:
   We have doxygen documentation of cling's code at:
http://cling.web.cern.ch/cling/doxygen/
--------------------------------------------------------------------------------
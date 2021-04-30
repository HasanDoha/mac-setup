
1. First, install Xcode from the App Store and command line tools using the terminal:
xcode-select --install
2. Next, install homebrew (if it is not installed)
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew doctor
brew update
3. Install packages needed to build meep:
brew install libunistring
brew install pkg-config
brew install libffi
brew install bdw-gc
brew install readline
brew install guile
brew install hdf5
brew install openblas
brew install fftw
brew install gsl
brew install swig
brew install automake
brew install autoconf
4. download source for libpng and after extracting it go to that directory and open a new terminal over there and run the following commands
./configure [--prefix=/path]
make check
make install
5. download source for the latest version of h5utils from github [https://github.com/NanoComp/h5utils] and after extracting it go to that directory and open a new terminal over there and run the following commands
sh autogen.sh
make
make install
6. download source for the latest version of harminv from github [https://github.com/NanoComp/harminv] and after extracting it go to that directory and open a new terminal over there and run the following commands
sh autogen.sh
make
make install
7. download source for the latest version of libctl from github [https://github.com/NanoComp/libctl] and after extracting it go to that directory and open a new terminal over there and run the following commands
sh autogen.sh
make
make install
8. download source for the latest version of mpb from github [https://github.com/NanoComp/mpb] and after extracting it go to that directory and open a new terminal over there and run the following commands
sh autogen.sh
make
make install
9. download source for the latest version of meep from github [https://github.com/NanoComp/meep] and after extracting it go to that directory and open a new terminal over there and run the following commands
sh autogen.sh
make
make install
10. Install python MEEP using pip
pip3 install meep

Links:
https://www.mail-archive.com/meep-discuss@ab-initio.mit.edu/msg05719.html
https://darkalexwang.github.io/2016/10/06/python-meep-install-mac/
https://www.mail-archive.com/meep-discuss@ab-initio.mit.edu/msg05292.html

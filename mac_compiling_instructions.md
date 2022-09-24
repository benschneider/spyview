```
brew install netpbm
brew install libpng
brew install fltk
brew install boost
```

then point to the right library locations where brew installs them:

```
export CXX="clang++"
export CXXFLAGS=$CFLAGS" -I/opt/homebrew/Cellar/fltk/HEAD-0fd10e9_1/include -I/opt/homebrew/Cellar/fltk/HEAD-0fd10e9_1/include/FL/images -isysroot /Library/Developer/CommandLineTools/SDKs/MacOSX12.sdk -D_LARGEFILE_SOURCE -D_LARGEFILE64_SOURCE -D_FILE_OFFSET_BITS=64 -D_THREAD_SAFE -D_REENTRANT"
export CPPFLAGS="-I/opt/homebrew/include/" # -I/opt/homebrew/Cellar/netpbm/10.86.34/"
export LDFLAGS="-L/opt/homebrew/lib/ -g"
export LDFLAGS=$LDFLAGS" -L/opt/homebrew/Cellar/boost/1.79.0_2/lib -lboost_serialization -lboost_serialization-mt"
export LDFLAGS=$LDFLAGS" -L/opt/homebrew/Cellar/netpbm/10.86.34/lib -lnetpbm.11"
export LDFLAGS=$LDFLAGS" -L/opt/homebrew/Cellar/libpng/HEAD-12222e6/lib -lpng16 -lz"
export LDFLAGS=$LDFLAGS" -L/opt/homebrew/Cellar/fltk/HEAD-0fd10e9_1/lib -lm -lpthread -framework Cocoa"
export LIBS="-L/opt/homebrew/lib/ -g"
export CPP="/usr/bin/cpp"
./configure --prefix=$HOME --datarootdir=${HOME}/.spyview $*
```

then run:
```
make
make install
```

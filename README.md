# UPDATES

- change build system to cmake from single makefile
- add clang-fomat
- remove vsproject files
- add include guard to `compoundfilereader.h`

---

# compoundfilereader

simple standalone c++ header file to read compound file (Structured Storage File) content.

## Source code structure

- **src/include/compoundfilereader.h**
  The only header file needed for parsing compound file.
- **src/include/utf.h**
  The helper header file used for converting between utf16, utf8, and unicode. It's used by samples.
- **test/data**
  Real world compound files for tests.
- **samples/cfb**
  command line tool to list and dump compound files.
- **samples/IEOpenedTabParser**
  command line tool to show IE opened tab information.
- **vsproject**
  project and solution files for Microsoft Visual Studio.

## Usage

- copy compoundfilereader.h to your source tree
  or: install "compoundfilereader" by git sub-module
- `#include "compoundfilereader.h"` in your source code
- construct a **CompoundFileReader** object by giving the buffer (see `compoundfilereader.h` for details)

## Build the samples

```shell
mkdir build
cd build
cmake ..
make
```

## Run the samples

try the following:

```shell
cd build
./ieot "../test/data/{BC59C035-E8AC-11E4-825B-10604B7CB9F0}.dat"
./cfb list "../test/data/a test email message.msg"
./cfb dump "../test/data/a test email message.msg" __properties_version1.0
```

### TODO

- [ ] unit tests
- [ ] make the reader able to connect to abstract interfaces such as istream

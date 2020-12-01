# AARCH64 EDK2 SCT Build Environment

git-repo Manifest for building the UEFI Self Certification Test (SCT) suite
from mainline edk2 and edk2-test for AARCH64 and ARM (32-bit)

## Usage

```bash
mkdir edk2-test-build
cd edk2-test-build
repo init -u https://github.com/glikely/edk2-test-manifest
repo sync
./build.sh
```

Build is 64-bit (AARCH64) by default.  To perform a 32-bit build pass the
parameter "ARM" to build.sh.
```bash
./build.sh ARM
```

To perform a 64-bit x86 build pass the parameter "X64" to build.sh.
```bash
./build.sh X64
```

A zip file will be created containing the SCT which can be unzipped onto a
flash drive

## Ccache

On a system where a ccache lib dir with symlinks exists, you can reuse
compilation results between builds by prepending the ccache lib dir to your
$PATH.
```bash
export PATH="/usr/lib/ccache:$PATH"
./build.sh
```

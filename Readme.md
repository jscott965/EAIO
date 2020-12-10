# EA IO

This is the EA IO package taken from EAWebKit 16.4.1.0.2 from https://gpl.ea.com/

EA IO is licensed under the BSD-3-Clause License, but does not exist on Electronic Arts' GitHub.
This version is slightly modified so it uses EASTL's allocator instead of coreallocator from EAWebKit.

# Usage

You can build using the provided CMake project. It depends on EASTL and EAAssert. If you do not include these targets, one will be provided from test/packages/EASTL as a git submodule.

You must have defined UTF_USE_EATRACE=0 UTF_USE_EAASSERT=1

There are other features defined EAIO/internal/Config.h that have not had ICoreAllocator patched 

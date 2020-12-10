# EA IO

This is the EA IO package taken from EAWebKit 16.4.1.0.2 from https://gpl.ea.com/

EA IO is licensed under the BSD-3-Clause License, but does not exist on Electronic Arts' GitHub.
This version is slightly modified so it uses EASTL's allocator instead of coreallocator from EAWebKit.

# Usage

This project includes a CMake project. It has a dependency on the EASTL and EAAssert target. If you do not include these targets, one will be provided from test/packages/EASTL as a git submodule.

You must have defined EASTL_CORE_ALLOCATOR_ENABLED=1 UTF_USE_EATRACE=0 UTF_USE_EAASSERT=1

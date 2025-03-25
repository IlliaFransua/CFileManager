# CFileManager 🦎

## Project Description

This project is a library for working with file storage. It includes functions for:
- Managing directories (creating, checking, deleting).
- Validating files.
- Generating unique paths to save files.
- Copying, deleting, and getting file information (like size and extension).
- Saving, loading, and updating file metadata (with UUID, file name, size, and timestamps).

**Note:** This project only provides tests to check the library’s functionality. How you use this tool (or library) in your projects is up to you.

## Features

- **File and Directory Management:**  
  Functions to create directories, check if a file exists, get file size, delete, and copy files.

- **Metadata Management:**  
  Ability to save, load, and update file metadata. The metadata includes:
    - `uuid` — unique file identifier.
    - `filename` — file name.
    - `size` — file size.
    - `created_at` — creation time.
    - `modified_at` — last modified time.

- **Utilities:**  
  Extra functions to check if a path is a directory, get a file extension, and more.

## Test Structure

The project has several test sets that cover all features:

1. **File Storage Tests:**
    - Create test directories and files.
    - Check file validation.
    - Generate unique paths and save files.
    - Clean up created files and directories.

2. **Metadata Tests:**
    - Test saving (`save_metadata`), loading (`load_metadata`), and updating (`update_metadata`) metadata.

3. **Utility Tests:**
    - Check if a path is a directory (`is_directory`).
    - Check if a file exists (`file_exists`).
    - Get file size (`get_file_size`).
    - Remove a file (`remove_file`).
    - Copy a file (`copy_file`).
    - Get file extension (`get_file_extension`).

## Build and Run Tests

### Building

The project uses CMake for build configuration. Here is an example of the build process:

```bash
mkdir build
cd build
cmake ..
make
```

Example build output:

```
-- The C compiler identification is Clang 19.1.7
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /opt/homebrew/opt/llvm/bin/clang - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Configuring done (0.5s)
-- Generating done (0.0s)
-- Build files have been written to: /Users/your_username/Projects/CFileManager/build
[ 11%] Building C object src/CMakeFiles/file_storage.dir/file_storage.c.o
[ 22%] Building C object src/CMakeFiles/file_storage.dir/metadata.c.o
[ 33%] Building C object src/CMakeFiles/file_storage.dir/utils.c.o
[ 44%] Linking C static library libfile_storage.a
[ 44%] Built target file_storage
[ 55%] Building C object tests/CMakeFiles/file_storage_tests.dir/file_storage_test.c.o
[ 66%] Building C object tests/CMakeFiles/file_storage_tests.dir/metadata_test.c.o
[ 77%] Building C object tests/CMakeFiles/file_storage_tests.dir/utils_test.c.o
[ 88%] Building C object tests/CMakeFiles/file_storage_tests.dir/main.c.o
[100%] Linking C executable file_storage_tests
[100%] Built target file_storage_tests
```

### Running Tests

Once the build is successful, you can run the tests with the following command:

```bash
./tests/file_storage_tests
```

Example output when running the tests:

```
File storage tests passed!
Metadata tests passed!
Utils tests passed!

All tests passed!
```

## Requirements

- C Compiler (e.g., gcc or clang)
- CMake
- POSIX Environment (for working with the file system)

## Usage and Conclusion

The library provides a set of functions for working with the file system and metadata, and the tests demonstrate the correctness and stability of all components. How to integrate the library into your application depends on your needs: you can use its full functionality or choose individual modules.

# CFileManager 🦎
CFileManager is a lightweight C library for managing file systems and file metadata. It provides a consistent API for:
- Creating, verifying, and deleting directories
- Validating file existence and structure
- Generating unique file paths for safe storage
- Copying and deleting files, and retrieving file attributes (e.g., size, extension)
- Reading, writing, and updating file metadata (UUID, name, size, timestamps)

> **⚠️ Note:** This project includes functional tests for validating the library's behavior. Integration and usage in production systems are left to the implementer.

## Features
- **File & Directory Operations:**  
  Create and delete directories, check file existence, retrieve file size, and copy files.
- **Metadata Handling:**  
  Store, retrieve, and update file metadata, including:
    - `uuid` – unique file identifier
    - `filename` – file name
    - `size` – file size
    - `created_at` – timestamp of creation
    - `modified_at` – timestamp of last modification
- **Utility Functions:**  
  Extra functions to check if a path is a directory, get a file extension, and more.

## Test Structure
The project includes comprehensive functional and integration tests that cover all features:
1. **File Storage Tests:**
    - Create and validate test directories and files
    - Generate unique paths and save files
    - Clean up test artifacts
2. **Metadata Tests:**
    - Validate saving (`save_metadata`), loading (`load_metadata`), and updating (`update_metadata`) metadata
3. **Utility Tests:**
    - Check if path is a directory (`is_directory`)
    - Verify file existence (`file_exists`)
    - Get file size (`get_file_size`)
    - Delete and copy files (`remove_file`, `copy_file`)
    - Get file extension (`get_file_extension`)

## Build & Run Tests
### Building
This project uses CMake for build configuration. To compile the project:
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
After a successful build, run the tests using:
```bash
./tests/file_storage_tests
```
Expected output:
```
File storage tests passed!
Metadata tests passed!
Utils tests passed!
All tests passed!
```

## Requirements
- C Compiler (e.g., gcc or clang)
- CMake
- POSIX Environment (for file system operations)

## Usage & Conclusion
This library offers functions for managing files, directories, and metadata. The included tests verify the correctness and stability of all components. Integration is flexible — you can use the entire library or select only the modules you need, depending on your application requirements.

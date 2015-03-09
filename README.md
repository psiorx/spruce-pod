# Spruce
Lightweight, Cross-platform Filesystem Wrapper Library for C++11

Platforms:
- Windows
- Mac
- Linux

## Example
Spruce is simple and straightforward.

```cpp
#import "spruce.hh"
#import <iostream>

spruce::path p( "test" );

if ( spruce::dir::mkdir( p ) )
{
std::cout << "Successfully created " << p;
}

```
## API

### Class `spruce::path`

| Return Type   | Member Function | Description                                  |
| :----------:  | ------------    | --------------                               |
|               | `setStr`        | set the path string                          |
| `std::string` | `getStr`        | get the path string                          |
| `std::vector` | `split`         | split the path on the directory delimeter    |
| `std::string` | `extension`     | get the extension, if there is one           |
| `std::string` | `root`          | get the root of the path                     |
| `bool`        | `isFile`        | identify if the path is a file               |
| `bool`        | `isDir`         | identify if the path is a directory          |
| `bool`        | `exists`        | identify if the path exists (file or folder) |
|               | `setAsTemp`     | set the instance to the temp directory       |
|               | `setAsHome`     | set the instance to the home directory       |
|               | `setAsCurrent`  | set the instance to the current directory    |

### Namespace `spruce::file`
All filesystem functions return a bool value denoting success or failure.

| Function        | Parameters                              |
| ----------      | :------------:                          |
| `remove`        | `spruce::path&`                         |
| `rename`        | `spruce::path&`, `spruce::path&`        |
| `copy`          | `spruce::path&`, `spruce::path&`        |
| `readAsString`  | `spruce::path&`  `std::string&`         |
| `writeAsString` | `spruce::path&`, `std::string&`, `bool` |

### Namespace `spruce::dir`
All filesystem functions return a bool value denoting success or failure.

| Function   | Parameters                       |
| ---------- | :------------:                   |
| `mkdir`    | `spruce::path&`                  |
| `mkdirAll` | `spruce::path&`                  |
| `rmdir`    | `spruce::path&`                  |
| `rename`   | `spruce::path&`, `spruce::path&` |
| `chdir`    | `spruce::path&`                  |

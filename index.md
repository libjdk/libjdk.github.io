---
layout: default
title: libjdk, make C++ still great
description: another way to write C++
---

## Overview

[**libjdk**](https://github.com/libjdk/libjdk) is a complete C++ reimplementation of the Java Development Kit, offering native performance while maintaining compatibility with Java's API design patterns. This project provides C++ libraries that correspond to Java's modular system, allowing developers to leverage Java's well-designed APIs in C++ applications.

## Features

- **Complete JDK Implementation**: Full implementation of Java's core libraries and modules
- **Cross-Platform Support**: Supports Windows, Linux, and macOS
- **Modular Architecture**: Follows Java's module system for clean separation of concerns
- **Native Performance**: C++ implementation provides better performance than JNI
- **Reflection Support**: Complete reflection API implementation for runtime type inspection and manipulation
- **High-Performance Garbage Collection**: Ultra-low latency automatic memory management with sub-millisecond pause times
- **CMake Build System**: Modern, cross-platform build configuration

## Supported Modules

The project includes implementations of the following Java modules:

### Core Modules
- [**java.base**](https://github.com/libjdk/java.base) - Core Java classes and utilities
- [**java.compiler**](https://github.com/libjdk/java.compiler) - Java compiler API
- [**java.logging**](https://github.com/libjdk/java.logging) - Logging framework
- [**java.xml**](https://github.com/libjdk/java.xml) - XML processing
- [**java.xml.crypto**](https://github.com/libjdk/java.xml.crypto) - XML cryptography

### Networking & Communication
- [**java.net.http**](https://github.com/libjdk/java.net.http) - HTTP client
- [**java.rmi**](https://github.com/libjdk/java.rmi) - Remote Method Invocation
- [**java.naming**](https://github.com/libjdk/java.naming) - Naming and directory services
- [**java.security.sasl**](https://github.com/libjdk/java.security.sasl) - SASL authentication
- [**java.security.jgss**](https://github.com/libjdk/java.security.jgss) - Generic Security Services

### Database & Transactions
- [**java.sql**](https://github.com/libjdk/java.sql) - Database connectivity
- [**java.sql.rowset**](https://github.com/libjdk/java.sql.rowset) - RowSet implementations
- [**java.transaction.xa**](https://github.com/libjdk/java.transaction.xa) - XA transaction support

### Desktop & UI
- [**java.desktop**](https://github.com/libjdk/java.desktop) - Desktop applications (Windows only)
- [**java.datatransfer**](https://github.com/libjdk/java.datatransfer) - Data transfer operations
- [**java.prefs**](https://github.com/libjdk/java.prefs) - User preferences

### Management & Monitoring
- [**java.management**](https://github.com/libjdk/java.management) - Management and monitoring
- [**java.management.rmi**](https://github.com/libjdk/java.management.rmi) - RMI-based management
- [**java.instrument**](https://github.com/libjdk/java.instrument) - Java instrumentation

### Additional Modules
- [**java.scripting**](https://github.com/libjdk/java.scripting) - Scripting engine
- [**jdk.compiler**](https://github.com/libjdk/jdk.compiler) - JDK compiler tools
- [**jdk.httpserver**](https://github.com/libjdk/jdk.httpserver) - HTTP server
- [**jdk.charsets**](https://github.com/libjdk/jdk.charsets) - Character set support
- [**jdk.localedata**](https://github.com/libjdk/jdk.localedata) - Locale data
- [**jdk.net**](https://github.com/libjdk/jdk.net) - Network utilities
- [**jdk.unsupported**](https://github.com/libjdk/jdk.unsupported) - Unsupported APIs
- [**jdk.zipfs**](https://github.com/libjdk/jdk.zipfs) - ZIP file system
- [**java.se**](https://github.com/libjdk/java.se) - Java SE platform (Windows only)

## Core Runtime Features

### Reflection Support

libjdk provides comprehensive reflection capabilities that allow runtime inspection and manipulation of classes, methods, fields, and annotations:

- **Class Introspection**: Get class information, superclasses, interfaces, and modifiers
- **Method Reflection**: Invoke methods dynamically, inspect method signatures and annotations
- **Field Access**: Read and modify field values, including private fields
- **Constructor Reflection**: Create object instances using constructor reflection
- **Annotation Processing**: Access and process runtime annotations
- **Generic Type Information**: Full support for Java generics and type parameters
- **Proxy Generation**: Dynamic proxy creation for interface implementations

### Garbage Collection

libjdk implements high-performance, low-latency automatic memory management:

- **Ultra-Low Latency**: Sub-millisecond pause times for real-time applications
- **High Throughput**: Optimized for maximum application performance
- **Predictable Pauses**: Bounded pause times for consistent application behavior
- **Memory Efficiency**: Advanced algorithms for optimal memory utilization
- **Automatic Memory Management**: No manual memory allocation/deallocation required
- **Memory Monitoring**: Built-in tools for monitoring memory usage and GC performance
- **Weak References**: Support for weak, soft, and phantom references
- **Finalization**: Automatic cleanup of resources when objects become unreachable

#### Performance Characteristics

- **Pause Time**: < 1ms for most operations
- **Throughput**: > 95% application time utilization
- **Scalability**: Efficient handling of large heaps (GB+)
- **Real-time Ready**: Suitable for latency-sensitive applications

## Requirements

- **CMake**: Version 3.30 or higher
- **C++ Compiler**: Supporting C++17 or later
- **Platform Support**:
  - Windows (x86_64)
  - Linux (x86_64)
  - macOS (x86_64, aarch64)

## Building

```bash
git clone --recursive https://github.com/libjdk/libjdk libjdk
mkdir build
cmake -S libjdk -B build -DCMAKE_BUILD_TYPE=Release -DINSTALL_TO_REPO=ON -DBUILD_TEST=ON -DJ=5
cmake --build build --config Release -j 3
```

## Hello World

After building and installing, you can use the libraries in your C++ projects:

```cpp
#include <jcpp.h>

int main() {
    $System::init();
    try {
        $System::out->println("hello, world"_s);
    } catch ($Throwable& e) {
        e->printStackTrace();
    }
    $System::deinit();
    return 0;
}
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass
6. Submit a pull request

## License

This project is licensed under the GNU General Public License v2.0 with the Classpath Exception. See the [LICENSE](https://github.com/libjdk/libjdk/blob/main/LICENSE) file for details.

## Acknowledgments

This project is based on the OpenJDK source code and follows Java's API design principles. Special thanks to the OpenJDK community for their excellent work on the Java platform.

## Version

Current version: 17.35

## Support

For questions, issues, or contributions, please refer to the project's issue tracker or contact the maintainers.
# File structure

```bash
src/lib/
├── factory
│   ├── docs
│   │   └── factory_class.mmd
│   ├── CMakeLists.txt
│   └── factory
│       ├── CMakeLists.txt
│       ├── IFactory.cpp
│       ├── IFactory.hpp
│       ├── impls
│       │   ├── CMakeLists.txt
│       │   ├── Factory.cpp
│       │   └── Factory.hpp
│       └── mocks
│       │   ├── CMakeLists.txt
│       │   └── MockedFactory.hpp
│       └── tests
│           ├── CMakeLists.txt
│           └── FactoryTestSuite.cpp
└── intergrtion-tests
    ├── CMakeLists.txt
    └── FactoryTestSuite.cpp # TODO: Create Suffix to integration tests
```

```cmake
# ${CMAKE_SOURCE_DIR}/src/lib/factory/impls/CMakeLists.txt

# NOTE: Sourcetrail implicit added as prefix
add_sourcetrail_library(
  NAME
  lib::factory::Factory
  SOURCES
  Factory.cpp
  PUBLIC_HEADERS
  Factory.hpp
  PRIVATE_DEPS
  Sourcetrail::core::utility::logging)
```

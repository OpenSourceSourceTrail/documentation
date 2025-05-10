# Software Requirements Specification (SRS)

## 1. Introduction

### 1.1 Purpose

This SRS outlines the functional and non-functional requirements for reviving Sourcetrail, an interactive source code explorer. The goal is to modernize the tool, address existing issues, and expand its capabilities to support contemporary development environments.

### 1.2 Scope

The project aims to:

* Restore and enhance Sourcetrail's functionality.
* Update dependencies and support modern platforms.
* Improve language support and indexing capabilities.
* Foster community contributions and long-term maintenance.

### 1.3 Definitions, Acronyms, and Abbreviations

* **Sourcetrail**: An interactive source code explorer.
* **SourcetrailDB**: The database format used by Sourcetrail.
* **LSP**: Language Server Protocol.
* **WSL**: Windows Subsystem for Linux.

### 1.4 References

* [Sourcetrail GitHub Repository](https://github.com/CoatiSoftware/Sourcetrail)
* [SourcetrailDB GitHub Repository](https://github.com/CoatiSoftware/SourcetrailDB)([GitHub][1])

## 2. Overall Description

### 2.1 Product Perspective

Sourcetrail is a cross-platform desktop application designed to aid developers in understanding and navigating complex codebases. It provides visualizations of code structures and relationships.

### 2.2 Product Functions

* Index source code to extract structural information.
* Visualize relationships such as call graphs and class hierarchies.
* Allow users to navigate and explore codebases interactively.([GitHub][2])

### 2.3 User Characteristics

* **Developers**: Primary users seeking to comprehend unfamiliar codebases.
* **Educators**: Individuals using the tool for teaching code structure and design.
* **Contributors**: Developers interested in extending or improving Sourcetrail.

### 2.4 Constraints

* Ensure compatibility with modern operating systems and development environments.
* Maintain modularity to facilitate community contributions.
* Adhere to open-source licensing requirements.

### 2.5 Assumptions and Dependencies

* Users have access to the source code they wish to analyze.
* Required development tools and environments are properly configured.([GitHub][3])

## 3. Specific Requirements

### 3.1 Functional Requirements

#### 3.1.1 Code Indexing

* Support indexing for C, C++, Java, and Python.
* Implement robust handling of complex build systems (e.g., Maven for Java).
* Enhance indexing accuracy and performance.

#### 3.1.2 Visualization

* Provide interactive visualizations of code structures, including call graphs and class hierarchies.
* Allow customization of visualization parameters (e.g., line thickness, color schemes).

#### 3.1.3 User Interface

* Modernize the UI to improve usability and accessibility.
* Ensure compatibility with high-DPI displays and dark mode themes.

#### 3.1.4 Integration

* Facilitate integration with popular IDEs and editors (e.g., VSCode, Visual Studio).
* Support remote indexing capabilities, including Docker and WSL environments.

### 3.2 Non-Functional Requirements

#### 3.2.1 Performance

* Optimize indexing and visualization processes for large codebases.
* Minimize application startup and response times.

#### 3.2.2 Reliability

* Ensure stable operation across supported platforms.
* Implement comprehensive error handling and logging mechanisms.

#### 3.2.3 Maintainability

* Structure the codebase to facilitate ease of maintenance and extension.
* Provide thorough documentation for developers and users.

#### 3.2.4 Portability

* Design the application to be easily portable to new platforms and environments.
* Support containerized deployments for consistent behavior across systems.

## 4. Appendices

### 4.1 Known Issues and Community Feedback

* **Java Indexing**: Users have reported issues with Maven projects indexing zero files.
* **Python Environment Detection**: Challenges in validating Python environments, particularly with Anaconda.
* **WSL Integration**: Crashes when indexing projects within WSL due to file permission issues.
* **Language Support Requests**: Community interest in adding support for languages like C# and JavaScript.

---

This SRS serves as a foundational document to guide the redevelopment and enhancement of Sourcetrail. Addressing the outlined requirements and known issues will position the project for renewed adoption and community engagement.

[1]: https://github.com/CoatiSoftware/SourcetrailDB?utm_source=chatgpt.com "GitHub - CoatiSoftware/SourcetrailDB: Library to export Sourcetrail ..."
[2]: https://github.com/CoatiSoftware/Sourcetrail/issues/885?utm_source=chatgpt.com "Every Maven project I try indexes 0 files #885 - GitHub"
[3]: https://github.com/CoatiSoftware/Sourcetrail/issues/1167?utm_source=chatgpt.com "Python projects indexing problem · Issue #1167 - GitHub"

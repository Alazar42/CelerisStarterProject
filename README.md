# Celeris Backend Framework Starter Project

![Celeris Logo](https://raw.githubusercontent.com/Alazar42/Celeris/refs/heads/main/docs/assets/celeris-main.png)

This repository serves as a starter template for building backend applications using the Celeris framework. Celeris is designed to provide a high-performance, modern, and efficient way to create APIs with C++.

## Features

- High-performance backend API handling
- Dynamic routing for GET and POST requests
- Built-in JSON serialization and deserialization
- Easy setup for new projects using Celeris

## Prerequisites

Before you begin, ensure you have the following installed:

- **C++ Compiler**: A C++ compiler that supports C++11 or later.
- **CMake**: To build the project.
- **Boost Libraries**: Required dependencies for Celeris, which are included in the project.

## Getting Started

Follow these steps to set up your Celeris backend project:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/YourUsername/Celeris-Backend-Starter.git
   cd Celeris-Backend-Starter
   ```

2. **Build the Project**:

   Create a build directory and compile the project:

   ```bash
   mkdir build && cd build
   cmake ..
   make
   ```

3. **Run the Application**:

   After building, you can run the server executable:

   ```bash
   ./your_server_executable
   ```

## Project Structure

```md
Celeris-Backend-Starter/
│
├── src/                # Source files
│   ├── main.cpp        # Entry point of your application
│   └── ...             # Other source files
│
├── include/            # Header files
│   └── ...             # Additional headers
│
├── CMakeLists.txt      # CMake configuration file
└── README.md           # Project documentation
```

## Example Usage

Here's a simple example to get you started with creating a server:

```cpp
#include <celeris/celeris.hpp>

int main() {
    Celeris app(8080, "127.0.0.1");

    // Define a simple GET route
    app.get("/hello", [](const Request& req, Response& res) {
        nlohmann::json json_response = {{"message", "Hello, Celeris!"}};
        res.set_json(json_response);
    });

    // Start the server
    app.listen();

    return 0;
}
```

## Documentation

For detailed documentation on using Celeris and its features, please refer to the [Celeris Documentation](https://github.com/Alazar42/Celeris/wiki).

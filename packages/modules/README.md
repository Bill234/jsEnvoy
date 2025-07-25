# @jsenvoy/modules

Core infrastructure for building modular tool systems. This package provides the essential base classes, dependency injection, and module management capabilities that enable the creation of extensible tool libraries.

## What This Package Provides

- **Base Classes**: Foundation classes for building tools and modules
- **Dependency Injection**: ResourceManager for managing dependencies
- **Module Factory**: Factory pattern for creating modules with resolved dependencies
- **Tool Infrastructure**: Everything needed to build tool systems

## Key Components

- `Tool` - Base class for tools that follow standard function calling format
- `ModularTool` - Base class for tools with dependency injection support
- `Module` - Container for related tools  
- `ResourceManager` - Dependency injection container
- `ModuleFactory` - Creates modules with dependency resolution

## Usage

```javascript
const { Tool, ModularTool, Module, ResourceManager, ModuleFactory } = require('@jsenvoy/modules');

// Create a tool
class MyTool extends ModularTool {
  constructor() {
    super();
    this.name = 'my_tool';
    this.description = 'My custom tool';
  }
  
  async execute(args) {
    return { result: 'success' };
  }
}

// Create a module
class MyModule extends Module {
  constructor() {
    super();
    this.name = 'my_module';
    this.tools = [new MyTool()];
  }
}
```

This package contains **infrastructure only** - actual tools are in `@jsenvoy/tools`.
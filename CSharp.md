### Table of Contents
 - [ ] The Philosophy of .NET
 - [ ] Building C# Applications
 - [ ] Core C# Programming Constructs, Part I
 - [ ] Core C# Programming Constructs, Part II
 - [ ] Understanding Encapsulation
 - [ ] Understanding Inheritance and Polymorphism
 - [ ] Understanding Structured Exception Handling
 - [ ] Working with Interfaces
 - [ ] Collections and Generics
 - [ ] Delegates, Events, and Lambda Expressions
 - [ ] Advanced C# Language Features
 - [ ] LINQ to Objects
 - [ ] Understanding Object Lifetime
 - [ ] Building and Configuring Class Libraries
 - [ ] Type Reflection, Late Binding, and Attribute-Based Programming
 - [ ] Dynamic Types and the Dynamic Language Runtime
 - [ ] Processes, AppDomains, and Object Contexts
 - [ ] Understanding CIL and the Role of Dynamic Assemblies
 - [ ] Multithreaded, Parallel, and Async Programming
 - [ ] File I/O and Object Serialization
 - [ ] Data Access with ADO.NET
 - [ ] Connected Layer
 - [ ] Disconnected Layer
 - [ ] Introducing Entity Framework 6
 - [ ] LINQ to XML
 - [ ] Introducing Windows Communication Foundation
 - [ ] Introducing Windows Workflow Foundation
 - [ ] Introducing Windows Presentation Foundation and XAML
 - [ ] WPF Controls, Layouts, Events, and Data Binding
 - [ ] WPF Graphics Rendering Services
 - [ ] WPF Resources, Animations, Styles, and Templates
 - [ ] Dependency Properties, Routed Events, and Templates
 - [ ] WPF Notifications, Validations, Commands, and MVVM
 - [ ] Introducing ASP.Net Web Forms
 - [ ] ASP.Net Web Controls, Master Pages and Themes
 - [ ] ASP.Net State Management Techniques
 - [ ] Introducing ASP.NET MVC
 - [ ] Introducing ASP.NET Web API
 - [ ] The Philosophy of .NET Core
 - [ ] Introducing Entity Framework Core
 - [ ] Introducing ASP.NET Core Web Applications
 - [ ] Introducing ASP.NET Core Service Applications

# Introducing C# and the .NET Platform
## The Philosophy of .NET

.Net can be understood as a runtime environment(CLR) and a comprehensive base class library. CLR locates, loads and manages .Net objects and also takes care of memory management, application hosting, coordinating threads, and performing basic security checks

CTS specification fully describes all possible data types and all programming constructs supported by the runtime, specifies how these entities can interact with each other, and details how they are represented in the .NET metadata format.

CLS, is a related specification that defines a subset of common types and programming constructs that all .NET programming languages can agree on.

.Net platform provides BCL that is available to all .Net programming languages

### C# Features

 - All Versions
   - No Pointers Required
   - Auto Memory Management (no `delete` keyword)
   - Operator overloading
   - Attribute `[ObsoleteAttribute]` based programming support
 - .Net 2.0
   - Generic Types and members
   - Anonymous methods (inline function)
   - `partial` keyword (used in class definition)
 - .Net 3.5
   - LINQ
   - Anonymous types
   - Extension methods
   - Lambda Operator (`=>`)
   - Set property value at Object Initialization `new Emp { Name = "DC Bhai" }`
 - .Net 4.0
   - Optional and Named method parameters
   - dynamic keyword
 - .Net 4.5
   - `async` and `await`
 - .Net 4.6 (C# 6)
   - Inline Initialization for automatic Properties
   - Readonly automatic properties
   - Single line method implementation
   - Support of static import
   - null conditional operator `?.`
   - string interpolation
   - `when` keyword to filter Exception
   - using `await` in `catch` and `finally` blocks
   - `nameOf` expressions
   - Index initializers
   - Improved Overload resolution
 - .Net 4.7 (C# 7)
   - Declate `out` variables as inline arguments
   - Nested function inside another function
   - Additional expression bodied members
   - Generalized `async` return types
   - New tokens to improve readability for numeric constants
   - Lightweight unnamed types (called `tuples`) that contain multiple fields
   - `ref` locals and returns
   - lightweight throwaway variables `discards`
   - Throw expressions
  - C# 7.1
   - Program's main method can be `async`
   - `default` allow for initialization of any type
   - tuple name can be inferred

## Building C# Applications
## Core C# Programming Constructs, Part I
## Core C# Programming Constructs, Part II
## Understanding Encapsulation
## Understanding Inheritance and Polymorphism
## Understanding Structured Exception Handling
## Working with Interfaces
## Collections and Generics
## Delegates, Events, and Lambda Expressions
## Advanced C# Language Features
## LINQ to Objects
## Understanding Object Lifetime
## Building and Configuring Class Libraries
## Type Reflection, Late Binding, and Attribute-Based Programming
## Dynamic Types and the Dynamic Language Runtime
## Processes, AppDomains, and Object Contexts
## Understanding CIL and the Role of Dynamic Assemblies
## Multithreaded, Parallel, and Async Programming
## File I/O and Object Serialization
## Data Access with ADO.NET
### Connected Layer
### Disconnected Layer
## Introducing Entity Framework 6
### LINQ to XML
## Introducing Windows Communication Foundation
### Introducing Windows Workflow Foundation
## Introducing Windows Presentation Foundation and XAML
## WPF Controls, Layouts, Events, and Data Binding
## WPF Graphics Rendering Services
## WPF Resources, Animations, Styles, and Templates
### Dependency Properties, Routed Events, and Templates
## WPF Notifications, Validations, Commands, and MVVM
### Introducing ASP.Net Web Forms
### ASP.Net Web Controls, Master Pages and Themes
### ASP.Net State Management Techniques
## Introducing ASP.NET MVC
## Introducing ASP.NET Web API
## The Philosophy of .NET Core
## Introducing Entity Framework Core
## Introducing ASP.NET Core Web Applications
## Introducing ASP.NET Core Service Applications

# Glossary
## Abbreviations
1. BCL   : Base Class Libraries
1. CIL : Common Intermediate Language
1. CLR : Common Language Runtime
1. CLS : Common Language Specification
1. COM : Component Object Model
1. CTS : Common Type System
1. JIT : Just In Time
1. LINQ : Language Integrated Query
1. VB : Visual Basic

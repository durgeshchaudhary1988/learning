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

.Net binaries (.dll or .exe) contains platform-agnostic Intermediate Language (IL) and type Metadata

C# code is compiled (using csc.exe) and Assembly is created which contains IL instructions which is then compiled on the fly into meaningful CPU instructions using JIT compiler. JIT compiler is leveraged by .Net Runtime and compiler is optimized for underlying platform.

Metadata contains documentation of all external assemblies required, version number, copyright info and so on.

### Types defined in CTS
 - CTS Class Types
 - CTS Interface Types
 - CTS Structure Types
 - CTS Enumeration Types
 - CTS Delegate Types

#### CTS Type Members
 - constructor
 - finalizer
 - static
 - constructor
 - nested type
 - operator
 - method
 - property
 - indexer
 - field
 - read-only field
 - constant
 - event

#### CTS Data Type
- System.Byte
- System.SByte
- System.Int16
- System.Int32
- System.Int64
- System.UInt16
- System.UInt32
- System.UInt64
- System.Single
- System.Double
- System.Object
- System.Char
- System.String
- System.Decimal
- System.Boolean

CLS is set of rules and one of the important being

 > CLS rules apply only to those part of a type that are exposed outside the defining assembly.

 In order to instruct compiler to check for CLS compliance use below statement

```csharp
[assembly: CLSCompliant(true)]
```

### CLR

CLR is runtime which is collection of services that are required to execute compiled unit of code. mscoree.dll is loaded automatically when an assembly is referenced for use.

 - Resolves location of assembly
 - Finding requested type within binary by reading metadata
 - Layout type in Memory
 - Compiles CIL into platform specific instructions
 - Perform security checks
 - Execute code

Namespace starting with `Microsoft` contain types that are used to interact with services unique to Windows Operating System.

### Open source .Net distributions

 - Mono
 - Xamarin SDK
 - .Net Core

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
> BCL : Base Class Libraries

> CIL : Common Intermediate Language (also called MSIL or IL)

> CLI : Common Language Infrastructure

> CLR : Common Language Runtime

> CLS : Common Language Specification

> COM : Component Object Model

> CTS : Common Type System

> GAC : Global Assembly  Cache (`C:\Windows\Assembly\GAC`)

> IL : Intermediate Language

> ILDASM : Intermediate Language Disassembler Utility

> JIT : Just In Time

> LINQ : Language Integrated Query

> MSIL : Microsoft Intermediate Language (also called IL or CIL)

> VB : Visual Basic

## Assemblies reference
> **csc.exe** compiler for C#

> **ildasm.exe** allows you to load up any .Net assembly and investigate its content.

> **mscoree.dll** Common Object Runtime Execution Engine

> **mscorlib.dll** Contains core types and core data types

> **ngen.exe**

> **vbc.exe** compiler for VB

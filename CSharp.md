### Table of Contents
 - [X] [The Philosophy of .NET](#the-philosophy-of-net)
 - [ ] Building C# Applications
 - [X] [Core C# Programming Constructs, Part I](#core-c-programming-constructs-part-i)
 - [ ] [Core C# Programming Constructs, Part II](#core-c-programming-constructs-part-ii)
 - [ ] [Understanding Encapsulation](understanding-encapsulation)
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

#### Points to note
 - All keywords are lowercase `public` `private` `lock` and so on
 - Namespace, Type and MemberName starts with InitCap `System` `SqlClient` `Main` `ReadLine` and so on
 - Returning 0 from Main means success else Error
 - By default Application returns 0 if nothing is returned from Program
 - Return value is stored in Environment Variable `%ERRORLEVEL%`

Following Main signatures are perfectly valid.

```csharp
static void Main();
static void Main(string[] args);
static int Main();
static int Main(string[] args);

// Async Main Methods starting C# 7.1
static Task Main();
static Task<int> Main();
static Task Main(string[] args);
static Task<int> Main(string[] args)
```

Sample Batch file to read `%ERRORLEVEL%`

```bash
SomeAppNameWithPath.exe
@if "%ERRORLEVEL%" == "0" goto success
:fail
  echo return value = %ERRORLEVEL%
  goto end
:success
  echo return value = %ERRORLEVEL%
  goto end
:end
```

Some Environment members

```csharp
Environment.ExitCode
Environment.Is64BitOperatingSystem
Environment.MachineName
Environment.NewLine
Environment.SystemDirectory
Environment.UserName
Environment.OSVersion
Environment.GetLogicalDrives()
Environment.ProcessorCount
Environment.Version
```

Both set of statements are equivalent
```csharp
var str = string.Format("{0}",Name);
Console.WriteLine(str);

Console.WriteLine("{0}",Name);
```

Some formatting examples
```
{0:c}    $99,999
{0:d9}   000099999
{0:f3}   99999.000
{0:n}    99,999.00
{0:E}    9.999900E+004
{0:e}    9.999900E+004
{0:X}    1869F
{0:x}    1869f
```
Declaring multiple variables
```
bool a = true, b = false, c = a;
```

> `default` literal is newly introduced in C# 7.1

```csharp
int x = default;
```

#### Data Type Class Hierarchy

 - Object
  - Value  Type
    - bool
    - int
    - char
    - decimal
    - DateTime
    - Enum and Structures
  - Type
  - String
  - Array
  - Exception
  - Delegate
    - MultiCastDelegate

#### Difference in Parse and TryParse
TryParse returns bool is successful and expects out parameter to be passed

#### BigInteger and Complex
> System.Numerics.dll defines structs named `BigInteger` and `Complex`
```csharp
BigInteger x = BigInteger.Parse("99999999999999999999999999999999999999999999999999");
BigInteger y = BigInteger.Multiply(x,BigInteger.Parse("88888888888888888888888888888888888888888888888888"));
var z = x * y;
x.IsEven;
x.IsPowerOf2;
```

#### Digit Separators
We can now write numbers separated with _(for int, long, double and decimal) for readability purpose. Both statements are equivalent in below example
```csharp
int i = 12_345;
long j = 98_582_123;
```

#### Binary Literals
Like Hexadecimal(0x) we can now define Binary(0b) numbers as well;
```csharp
int i = 0b0001000;
int j = 0b00_101_110;
```

#### Equality Checks
When we check for equality (== or !=) in case of reference type objects, their reference are compared if they are pointing to same object. In case of string they are overridden to check for content;
```csharp
Employee e1 = new Employee();
Employee e2 = new Employee();

e1 == e2; // returns false

string s1 = "Durgesh";
string s2 = "Durgesh";

s1 == s2; // returns true
```
#### Immutable strings
> Strings are immutable i.e. once a string has been initialized it can not be changed, a new string is generated everytime.

#### String Interpolation

```csharp
string s1 = string.Format("{0} is a {1}",name,gender);
string s2 = $"{name} is a {1}";
string s3 = $"Hello {name.ToUpper()}, you  are a {gender}";
```

#### Type Conversion

```csharp
int Add(int a, int b)
{
  return a + ;
};
byte x = 10;
byte y = 10;
Add(x,y); // Auto Widening
byte z =Add(x,y); // Compile Time Error

byte p = (byte)Add(x,y); // It works fine Explicit Type Conversion

x = 100;
y = 250;
Add(x,y); // Auto Widening
byte p = (byte)Add(x,y); // Incorrect Value with no OverFlow Error

p =checked((byte)Add(x,y)); // Exception if overflow

checked
{
  // Multiple statements where checked needs to be allowed
  unchecked
  {
    // Ignore check
  }
}
```

`var` keyword is used to implicitly declare variables and can be used only inside Methods or Properties. It can not be used as return type and field members.

`?:` is conditional Operator

`switch` cases must have break, return or goto to avoid falling through next statement

`switch` now also supports pattern matching and can then be combined with condition as well. e.g.

```csharp
object o = "SomeString"; // or 85 or 85.95
switch(o)
{
  case int i when i == 85:
    // if o is int and equals 85
    break;
  case int i:
    // if o is int and not equals 85
    break;
  case string s:
    // if o is string
    break;
  case double d:
    // if o is double
    break;
}
```

## Core C# Programming Constructs, Part II
## Understanding Encapsulation
 - In class fields should not be defined as public but defined private
 - Properties should be created to provide controlled access
 - Methods can now be defined using Expression e.g. `void Do() => Console.WriteLine("Doing");`
 - constructors can now be defined using Expression e.g. `public Employee(string name) => Name = name;`
 - constructors can be chained using this keyword e.g.
 ```csharp
 public Employee():this(null,0){}
 public Employee(string name):this(name,0){}
 public Employee(int age):this(null,age){}
 public Employee(string name,int age)
 {
      Name = name;
      Age = age;
 }
 ```

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

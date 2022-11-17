### Concepts
Variable is a placeholder of the information which can be changed at runtime. And variables allow to Retrieve and Manipulate the stored information. In Go, variables are explicitly declared and used by the compiler to e.g. check type-correctness of function calls.

### Rules for Naming Variables:

- Variable names must begin with a letter or an underscore(_). And the names may contain the letters ‘a-z’ or ’A-Z’ or digits 0-9 as well as the character ‘_’.
```go
    Variables, variables, _variable123  // valid variable
    123Variables, 23variables      // invalid variable
```
    
- A variable name should not start with a digit.
```go
    234variables  // illegal variable 
```
    
- The name of the variable is case sensitive.

```go
    variables and Variables are two different variables
```

- Keywords is not allowed to use as a variable name.
- There is no limit on the length of the name of the variable, but it is advisable to use an optimum length of 4 – 15 letters only.
- capitalize acronyms(HTTP, URL)(Pascal or camelCase)
- longer names for longer lives(as short as reasonable)

### Declare

There are three ways to declare variables in Go:
1. Declare the variable with `var` keyword, then assign value to it
```go
    var i int
    i = 10
```

2. Declare and initialize value simultaneously:
```go
    var i int = 10
```

3. Declare and initialize value simultaneously using shorthand syntax:
```go
    i := 10
```

### Characteristics

- cannot redeclare variable but can shadow it
- all variables must be used(if not throw error)
- visibility
    - lower case first letter for package scope
    - upper case first letter to export
    - no private scope
- type conversions
    - destination Type(variable)
    - use strconv package for strings
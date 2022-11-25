### Concepts
Defer, Panic and Recover are essential concepts when developing Go applications. With the `defer` function, you are able to call a function but prevent execution until some other functions are executed. If you are familiar with Python language, the `defer` function is similar to finally keyword in Python.
For your Go application to `panic`, it has to come to a point where it cannot run anymore because it doesn't know what to do. This can be triggered by the compiler or manually in our code.
As for the `recover` keyword, it is closely related with `panic`. When a program enters a panic state we have an option to help it recover from that, we use the `recover` keyword.

1. Defer
The `defer` statement enables you to prevent the execution of a function until a later time, depending on what you are trying to accomplish.
Using a real-world example, growing up every guy has the ability to grow beards but that ability is held for some reason till you are older. Basically, that is how `defer` works.

2. Panic
`panic` is a built-in function that stops the control flow of your program. This can be done by the compiler or added manually to your code flow.
We use panic statements when your application enters a state that it cannot recover from. Example: Trying to divide a number by 0.
They occur when the program can’t continue at all.

3. Recover
`recover` function is used to recover function from `panic`. Recover is only useful inside deferred functions. In a normal execution, a call to recover will returnniland have no other effect. A `recover` function should always be called inside a defer function because the deferred function does not stop its execution if the program panics, so the `recover` function stops the panicking.

### Properties and notes
1. Defer
- Defer statement doesn’t run a function, it runs the function call.
- It follows last in, first out order(LIFO), i.e., the last defer statement that is called will be the first to be executed.
- Used to delay execution of a statement until function exists
- Useful to group 'open' and 'close' functions together
  - be careful in loops
- Arguments evaluated at time defer is executed, not at the time of called function execution

2. Panic
- Panics happen after a deferred statement is executed.
- the program ends after the panic statement is run.
- Occur when program cannot continue at all
  - Don't use when file can't be opened, unless it is critical
  - Use for unrecoverable events - cannot obtain TCP port for web server
- Function will stop executing
  - Deferred functions will still fire
- If noting handles panic, program will exist

3. Recover
- Recovery statements are used to come out of a panic
-  Useful inside deferred functions. This is because when an application panics, it no longer executes the rest of the program except for deferred functions.
- Current function will not attempt to continue, but higher functions in call stack will

### How to use
1. Defer
```go
package main
import("fmt")func main() {
         fmt.Println("one")
         defer fmt.Println("three")
         fmt.Println("two")}
```

Output:
```go
one
two
three
```

2. Panic
```go
package main
import "fmt"func main(){
        fmt.Println("one")
        defer fmt.Println("three")
        panic("a panic happened")
        fmt.Println("four")}
```

Output:
```go
one
three
panic: a panic happened
```

3. Defer
```go
package mainimport "fmt"func main() {
  x := 0
  y := 20
  printAllOperations(x, y)
}func printAllOperations(x int, y int) {defer func() {
 // defer function to escape the panic when y/x runs
    if r := recover(); r != nil {
      fmt.Printf("Recovering from panic in printAllOperations error is: %v \n", r)
      fmt.Println("Proceeding to alternative flow skipping division.")
      printOperationsSkipDivide(x, y)
    }
  }()sum, divide, multiply := x+y, y/x, x*y
  fmt.Printf("sum=%v, divide=%v, multiply=%v \n", sum, divide, multiply)
} func printOperationsSkipDivide(x int, y int) {
  sum, multiply := x+y, y*x
  fmt.Printf("sum=%v, multiply=%v \n", sum, multiply)
}
```

Output:
```go
Recovering from panic in printAllOperations error is: runtime error: integer divide by zero 
Proceeding to alternative flow skipping division.
sum=20, multiply=0
```

*Reference* https://medium.com/analytics-vidhya/defer-panic-and-recover-control-flow-concepts-in-go-c84265a05993
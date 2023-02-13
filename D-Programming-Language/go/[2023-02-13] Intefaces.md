## Context
Interfaces define behavior, structs define data 

## Best practices

<aside>
💡 Use many, small interfaces

- Single method interfaces are some of the most powerful and flexible:
    - io.Writer, io.Reader, interface{}
</aside>

<aside>
💡 Don't export interfaces for types that will be consumed

</aside>

<aside>
💡 Do export interfaces for types that will be used by package

</aside>

<aside>
💡 Design functions and methods to receive interfaces whenever possible

</aside>

- Basics
    
    ```go
    type Writer interface {
    	Write([]byte)(int, error)
    }
    
    type ConsoleWriter struct {}
    
    func (cw ConsoleWriter) Write(data []byte)(int, error) {
    	n, err := fmt.Println(string(data))
    	return n, err
    }
    ```
    
- composing interfaces
    
    ```go
    type Writer interface {
    	Write([]byte)(int,error)
    }
    type Closer interface {
    	Close() error
    }
    type WriterCloser interface {
    	Writer
    	Closer
    }
    ```
    
- Type conversion
    
    ```go
    var wc WriterCloser = NewBufferedWriterCloser()
    bwc := wc.(*BufferedWriterCoser)
    ```
    
- The empty Interface and type switches
    
    ```go
    var i interface() = 0
    switch i.(type) {
    	case int:
    		fmt.Println("i is an interger")
    	case string:
    		fmt.Println("i is a string")
    	default:
    		fmt.Println("I don't know what I is")
    }
    ```
    
- Implementing with values vs pointers
    - Method set of value is all methods with value receivers
    - Method set of pointer is all methods, regardless of receiver type
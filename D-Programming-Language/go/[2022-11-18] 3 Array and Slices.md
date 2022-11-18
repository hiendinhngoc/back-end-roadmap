### Concepts
In Go, arrays and slices are data structures that consist of an ordered sequence of elements. These data collections are great to use when you want to work with many related values. They enable you to keep data together that belongs together, condense your code, and perform the same methods and operations on multiple values at once.

### array
- collection of items with same type
- fixed size
- declaration styles:
    - `a := [3]int{1,2,3}`
    - `a := [...]int{1,2,3}`
    - `var a [3]int`
- access via zero-based index
    - `a := [3]int {1,2,3}` // a[1] == 2
- `len` function returns size of array
- copies refer to different underlying data

### slice
- backed by array
- creation styles
    - slice existing array or slice
    - literal style
    - via make function
        - `a := make([]int, 10)`
        - `a := make([]int, 10, 100)`
    - `len` func return length of slice
    - `cap` func returns length of underlying array
    - `append` func to add elements to slice
        - may cause expensive copy operation if underlying array is too small
    - copies refer to same underlying array
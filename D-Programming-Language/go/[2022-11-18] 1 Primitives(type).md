### Concepts
We have four different groups of useful primitive types, namely Text, Numeric, and Boolean type.

#### Boolean
- `bool`
- values are true or false
- not an alias for other type(int)
- zero value is false

### Numeric
#### Integers
- signed integer(`int` `int8` `int16` `int32` `int64`)
    - `int` type has varying size, but min 32 bits
    - 8 bit(`int8`) though 64 bit(`int64`)
- unsigned integers(`uint` `uint8` `uint16` `uint32` `uint64` `uintptr`)
    - 8 bit(byte and `unit8`) though 32 bit(`unit32`)
- arithmetic operations
    - addition, subtraction, multiplication, division, remainder
- bitwise operations
    - `and`, `or`, `xor`, and `not`
- zero value is `0`
- **can't mix types in same family!(unit16 + unit32 = error)**

#### Floating point number(`float32` `float64`)
- follow IEEE-754 standard
- zero value is 0
- 32 and 64 bit version
- literal styles
    - decimal(3.14)
    - exponential(13e18 or 2E10)
    - mixed(13.7e12)
- arithmetic operations
    - addition, subtraction, multiplication, division

#### complex number(`complex64` `complex128`)
- zero value is (0+0i)
- 64 and 128 bi versions
- built-in function
    - complex - make complex number from two floats
    - real - get real part as float
    - imag - get imaginary part as float
- arithmetic operations
    - addition, subtraction, multiplication, division

### Text
#### Strings(Double quote)
- UTF-8
- immutable
- can be concatenated with (+) operator
- can be converted to []byte

#### Rune(Single quote)
- UTF-32
- alias for int32
- special methods normally required to process
    - e.g strings.Reader#ReadRune
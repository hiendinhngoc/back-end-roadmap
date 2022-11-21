### Concepts
- Golang Maps is a collection of unordered pairs of key-value. It is widely used because it provides fast lookups and values that can retrieve, update or delete with the help of keys.
- A structure or struct in Golang is a user-defined type that allows to group/combine items of possibly different types into a single type. Any real-world entity which has some set of properties/fields can be represented as a struct. This concept is generally compared with the classes in object-oriented programming. It can be termed as a lightweight class that does not support inheritance but supports composition.

### Characteristics

#### Map
- collections of value types that are accessed via keys
- created via literals or via `make` function
- members accessed via [key] syntax
    - myMap["key"] = "value"
- check for presence with "value, ok" form of result

#### Struct
- collections of disparate data types that describe a single concept
- keyed by name fields
- normally created as types, but anonymous structs are allowed
- structs are value types
- no inheritance, but can use composition via embedding
- tags can be added to struct fields to describe field

### When to use

#### The time to use a Map:
  - All keys must be the same type
  - All values must be the same type
  - Keys are indexed – we can iterate over them
  - Use to represent a collection of related properties
  - Don’t need to know all the keys at compile time
  - Reference Type

#### The time to use a struct
  - Values can be different type
  - Keys don’t support indexing
  - You need to know all the different fields at compile time
  - Use to represent a “thing” with a lot of different properties
  - Value Type
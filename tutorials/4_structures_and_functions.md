# Structures and Functions

## Types

Since types for variables are implicit you usually don't have to specify them. The exception is when creating your own data structures and functions. When Types are always enclosed in {}.

## Data Structures

Structures must be constants, so they are always delared with `::`. Your new type should be one or more other types inclosed in {}. Here is an example:

```
myType :: {Int, Dub}
```

The comma that seporates them is only for readability. It could be a semicolon, newline or just a space (NOTE: inside types is the only place a comma is interchangable with anything else). The elements in a data structure always have names. If none is specified, they are given the names `a`, `b`, `c`, etc. like tuples. You can specify your own names with `:`. For example:

```
myType :: {name1: Int, name2: Bool}
```

As long as the types match up, tuples and structures can be implicitly converted to eachother.

## Functions

Functions must currently be declared as constants. In the future, non constant functions (aka lambda expressions) will be possible. The types a function takes and returns must be explicity stated in the header. A function header looks like this `{leftInput}.{rightInput} -> {returnType}`. The header should be followed by a colon and a perenthesis enclosed list of statements.

### Input and Output
The left input and return type can be omitted, in wich case they are `Void`. If you want the right input to be `Void`, simply leave the {} empty. Right input is the type of input you are already used to. Left input is a concept that is somewhat unique to Pinecone. It is just like right input, except that you call the function with `input.function` instead of `function: input`. A function can take both left and right input. The right input is named `in` and the left is named `me`. There is currently no return syntax in Pinecon, instead return value is the last expression in the function.

### Examples

```
addOne :: {Int} -> {Int}:
(
    a: in+1
    a
)

printNumbers :: {val1: Dub, val2: Dub}:
(
    print: in.val1
    print: in.val2
)
```

I know the `in.` is annoying. It will be made implicit soon.

[index](index.md) | [next: Transpiling to C++ ->](5_transpiling_to_cpp.md)

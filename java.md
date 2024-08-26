# Java

Similarly to Go, I would normally avoid putting a cheat sheet for general language things. However, because I don't use Java often, I'd like to make note of how to do things in Java I often do in C#, etc.

## C# `foreach`

```java
for (int item : collection) { }
```

TODO: Research backend for this syntax.
Does `item` have to be a `Collection`? Implement an interface? Just have `MoveNext method?

## LINQ

The drop-in LINQ for Java are Java Streams.

### Create

#### Arrays

```java
Arrays.stream(arr)
```

#### Collections

```java
collection.stream()
```

## Functions as Data

### Lambda syntax

`->`

### C# `Func`

From what I have found, there is no drop-in C# `Func` in Java. There is `Function<T, R>` and `Supplier<T>` for a function that takes no arguments.

### Method Reference Operator

If you want to reference a method to, for example, pass to a Stream function, you can reference it with the `::` operator.

For example

```java
List.of("a", "b").stream().forEach(System.out::println);
```

## Parsing

When parsing numbers, use static methods in their boxed types:

In general

```java
Number.parseNumber("4")
```

For example

```java
Double.parseDouble("0.01")
```

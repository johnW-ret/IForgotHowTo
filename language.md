# Quick reference of common data structures across base class libraries of multiple languages

| Data Structure | C#                                                       | Java                               | Python     | Notes    |
| -------------- | -------------------------------------------------------- | ---------------------------------- | ---------- | -------- |
| List           | `new List<int>()`                                        | `new ArrayList<Integer>()`         | `[]`       |
| Dictionary     | `new Dictionary<TKey, TValue>()`                         | `new HashMap<Key, Value>()`        | `{}`       |
| Records        | `public record Record(String Name) [{ /* members */ }];` | `public record Record(String Name) { /* members */ }` | potentially using `namedtuple` or `dataclass`; need to do more research | members become properties in C# (accessed without `()`); members become methods in Java (accessed with `()`).

> C# has `IDictionary` and Java has `Map`, what's the best way to incorporate interfaces into the table reference?

> `[]` in Records:C# means *optional*; is there a clearer way to state this?
EF Core
=======

# Collections
- As of behavior I observed on EF Core 8 with SQLite, *collection navigations that point to empty tables will defualt to `null`*, not an empty instance that implements `ICollection`. Therefore, [you should always give collection navigation properties a default value](https://learn.microsoft.com/en-us/ef/core/modeling/relationships/navigations#initialization-of-collection-navigations) (though preferably with `[]`), [since they should never be null](https://learn.microsoft.com/en-us/ef/core/miscellaneous/nullable-reference-types#required-navigation-properties). 


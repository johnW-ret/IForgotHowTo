EF Core
=======

# Collections
- As of behavior I observed on EF Core 8 with SQLite, *collection navigations that point to empty tables will defualt to `null`*, not an empty instance that implements `ICollection`. Therefore, [you should always give collection navigation properties a default value](https://learn.microsoft.com/en-us/ef/core/modeling/relationships/navigations#initialization-of-collection-navigations) (though preferably with `[]`), [since they should never be null](https://learn.microsoft.com/en-us/ef/core/miscellaneous/nullable-reference-types#required-navigation-properties). 

# Identity
> More of an Identity topic and not an EF topic? but related enough to include here

## EF Core `Include` on `ApplicationUser` retrieval using `UserManager`
[`UserManager<TUser>.GetUserId(ClaimsPrincipal)`](https://learn.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.identity.usermanager-1.getuserid?view=aspnetcore-8.0) should be used instead of `GetUserAsync` when naivagation properties need to be loaded with `Include` on the `ApplicationUser`, because `GetUserId` should just read from the `ClaimsPrincipal` and not hit the database (TODO: test manually).
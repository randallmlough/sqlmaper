# GO SQLMapping 
A simple helper library to map arbitrary `map[string]interface{}` data to a struct. It supports deep embedding of structs among many other things. The original use case for this library/helper is to map SQL data to structs and json column data.

## Options
### Tables:
There's a couple ways to handle tables.
First you can use a struct tag like `scan:"notate"`. This tag will reduce and dot notate a struct to "table_one.column". You as the developer will most likely never need to worry about the naming scheme here, but for mapping embedded structs where the data is transmitted in dot notation (ie. table_one.id, table_one.name, table_two.email, etc.), which is useful for join tables, this is necessary. 
Dot notation can be turned on by default by calling `sqlmaper.NotatedByDefault(true)`.


Initial groundwork was done by Doug Martin and his awesome [goqu](github.com/doug-martin/goqu) go SQL query builder library.
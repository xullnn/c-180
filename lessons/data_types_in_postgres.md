1. Describe the difference between the `varchar` and `text` data types.

In common:
- they both store string up to unlimited size(practical meaning)

Diff:
- we could specify char length for `varchar(25)` but we don't do this to `text`
- `varchar()` is a predefined type in SQL but `text` is a type defined by PostgreSQL, but some other RDBMs also have `text`

https://www.postgresql.org/docs/11/datatype-character.html

2. Describe the difference between the integer, decimal, and real data types.

In common:
- they are all numeric types
- every type may be configure to take certain bytes of space in different RDBMs, so they probably have limit on value.
- The types `decimal` and `numeric` are equivalent. Both types are part of the SQL standard.

Diff:
- `integer` handles whole numbers
- `decimal` and `numeric` are **Arbitrary Precision Numbers** type, they handle fixed-point number
- `real` is one of **Floating-Point Types**, it handles float-point numbers.

https://www.postgresql.org/docs/11/datatype-numeric.html#DATATYPE-NUMERIC-DECIMAL

3. What is the largest value that can be stored in an `integer` column?

`	-2147483648 to +2147483647`

4. Describe the difference between the `timestamp` and `date` data types.

`timestamp` includes date part and time part(e.g `'1999-09-09 04:05:06'`), `date` only includes `date` part(e.g `'1999-09-09'`).

https://www.postgresql.org/docs/11/datatype-datetime.html

5. Can a time with a time zone be stored in a column of type timestamp?

No. By default if we use `timestamp` as a columns type, actually we get `timestamp without time zone` if we want to include time zone we could use `timestamp with time zone` or `timestamptz`

https://www.postgresql.org/docs/11/datatype-datetime.html

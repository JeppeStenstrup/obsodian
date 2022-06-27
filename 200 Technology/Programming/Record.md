[[C Sharp]]

# Record

- C# 9 introduces records, a new reference type for encapsulating data developers can use instead of classes and [[Struct|structs]].
- Record instances can have immutable properties through the use of pre-initialized positional parameters.
- Record types have a compiler-generated ToString method that returns the names and values of public properties and fields in an instance.
- Differently from [[Class|classes]], _equality_ in Records doesn't necessarily mean reference equality. Two record instances are equal if the values of all their properties and fields are equal.
- Non-destructive mutation allows the creation of new record instances from existing immutable records. 
- Records can be inherited.

Example of implementation:
```cs:C#
public record CreateOrder : ICommand<string>
{
    public int Id { get; set; }
    public int CustomerId { get; set; }
}
public record GetOrder : IQuery<order>
{
    public int OrderId { get; set; }
}
```
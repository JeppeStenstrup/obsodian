[[C Sharp]]

# MediatR

## Pattern
With MediatR, we implement _commands_.
We do this by defining a class that implements the `IRequst<T>` interface, where `T` is the return type for the command.

```cs:C#
public class CreateUser : IRequest<string>
{
	public string id { get; set; }
	public string Name { get; set; }
}
```

To send the command to from ASP.NET Core API to the MediatR, we can use this code:
```cs:C#
[Route("api/[controller]")]
[ApiController]
public class CommandController : ControllerBase
{
    private readonly IMediator _mediator;
    public CommandController(IMediator mediator)
    {
        _mediator = mediator;
    }
    [HttpPost]
    public async Task<string> Get(CreateUser command)
    {
        return await _mediator.Send(command);
    }
}
```

On the receiving end, we create a class that implements the `IRequestHandler<T,U>` interface, where `T` is the command-type, and `U` is the [[CancellationToken]].
```cs:C#
public class CommandHandlers : IRequestHandler<createuser, string="">
{
    public Task<string> Handle(CreateUser request, 
                               CancellationToken cancellationToken)
    {
        return Task.FromResult("User Created");
    }
}
```

## CQRS
![[Command Query Responsibility Segregation]]

## Combining MediatR and CQRS
Combining these two patterns allows us to create an architecture that looks like this:
![[MediatR_CQRS.webp]]

## Commands and Queries
With MediatR we have no clear separation between commands and queries, because both implements `IRequest<T>`, but to accommodate this we introduce the following helper interfaces:
```cs:C#
public interface ICommand<T> : IRequest<T>
{
}
public interface IQuery<T> : IRequest<T>
{
}
```

Which can be utilized in the following way, using C#9's new [[Record|records]]:
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

## Commands and Queries in the Frontend
To utilize these new records, we need to make a frontend that can call them:
```cs:C#
[Route("api/[controller]")]
[ApiController]
public class CommandController : ControllerBase
{
    private readonly IMediator _mediator;
    public CommandController(IMediator mediator)
    {
        _mediator = mediator;
    }
    [HttpPost]
    public async Task<string> CreateOrder([FromBody] CreateOrder command)
    {
        return await _mediator.Send(command);
    }
    [HttpPost]
    public async Task<order> GetOrder([FromBody] GetOrder command)
    {
        return await _mediator.Send(command);
    }
}
```

We can now, using HttpPost call to fire the commands.[^1]

[^1]: [[Parameter Binding]]
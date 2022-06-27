[[C Sharp]]

# Parameter Binding

## [FromUri]
### Class:
```cs:C#
public class StudentController : ApiController
{
    public Student Post([FromUri]int id, string name, string color)
    {

    }
}
```

### Request
```cs:C#
https://reqres.in/api/user/2
---
{
    "data": {
        "id": 2,
        "name": "fuchsia rose",
        "year": 2001,
        "color": "#C74375",
        "pantone_value": "17-2031"
    },
    "support": {
        "url": "https://reqres.in/#support-heading",
        "text": "To keep ReqRes free, contributions towards server costs are appreciated!"
    }
}
```

## [FromBody]
### Class:
```cs:C#
public class StudentController : ApiController
{
    public Student Post([FromBody]string name, string id, string createdAt)
    {

    }
}
```

### Request
```json:POST-request
https://reqres.in/api/users
{
  "name": "fuchsia rose"
}

---
{
    "name": "fuchsia rose",
    "id": "2",
    "createdAt": "2022-05-30T09:11:54.393Z"
}
```
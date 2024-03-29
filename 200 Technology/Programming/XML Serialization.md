[[C Sharp]]

# XML Serialization
Serialize an XML document into C# objects.
```cs:C#
using System.Xml.Serialization;
```

## Further
- [[XML Arrays]]

## Tasks
- [[Xml configs to serialize]]


## Example

```xml:XML(Cars.xml)
<Cars>
  <Car>
    <StockNumber>1020</StockNumber>
    <Make>Nissan</Make>
    <Model>Sentra</Model>
  </Car>
  <Car>
    <StockNumber>1010</StockNumber>
    <Make>Toyota</Make>
    <Model>Corolla</Model>
  </Car>
  <Car>
    <StockNumber>1111</StockNumber>
    <Make>Honda</Make>
    <Model>Accord</Model>
  </Car>
</Cars>
```

```cs:C#(Entities/cars.cs)
[XmlRoot("Cars")]
public class Cars
{
	List<Car> cars {get; set;}
}

public class Car
{
	string StockNumber {get; set;}
	string Make {get; set;}
	string Model {get; set;}
}
```

```cs:C#
List<Cars> cars = new();

XmlSerializer serializer = new XmlSerializer(typeof(Cars));
using (TextReader reader = new StringReader("Cars.xml"))
{
	cars = serializer.Deserialize(reader) as List<Cars>;
}
```
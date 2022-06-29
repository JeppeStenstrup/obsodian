[[XML Serialization]]

# XML Arrays

```xml:XML
<linksetup link="bdout">
	<defaultvalues>
		<values>
			<value comment="Auto">Automatic</value>
			<value comment="Transfering">FollowFlag</value>
			<value comment="Ready">Manual</value>
		</values>
	</defaultvalues>
	<transferstrategies>
		<originate id="default">
			<imarket>
				<filter name="default">
					<strategy>
						<transfermode>FollowFlag</transfermode>
						<transferstate>Created</transferstate>
					</strategy>
				</filter>
			</imarket>
		</originate>
		...
		<originate id="default">
			<imarket>
				<filter name="default">
					<strategy>
						<transfermode>FollowFlag</transfermode>
						<transferstate>Created</transferstate>
					</strategy>
				</filter>
			</imarket>
		</originate>
	</transferstrategies>
</linksetup>
```

```cs:C#
[XmlRoot("linksetup")]
public class Root
{
	[XmlAttribute("link")]
	public string link { get; set; }
	
	public DefaultValues defaultvalues { get; set; }
	
	[XmlArray("transferstrategies")]
	[XmlArrayItem("originate", typeof(Originate))]
	public Originate[] transferstrategies { get; set; }
}

/* DefaultValues */

public class DefaultValues
{
	[XmlArray("values")]
	[XmlArrayItem("value", typeof(Value))]
	public Value[] values { get; set; }
}

public class Value
{
	[XmlAttribute]
	public string comment { get; set; }
	
	[XmlText]
	public string value { get; set; }
}

/* TransferStrategies */

public class Originate
{
	[XmlAttribute]
	public string id { get; set; }

	[XmlElement(ElementName = "imarket")]
	public IMarket imarket { get; set; }
}

public class IMarket
{
	[XmlElement(ElementName = "filter")]
	public Filter filter { get; set; }
}

public class Filter
{
	[XmlAttribute]
	public string name { get; set; }

	[XmlElement(ElementName = "strategy")]
	public Strategy strategy { get; set; }
}

public class Strategy
{
	[XmlElement(ElementName = "transfermode")]
	public string transfermode { get; set; }
	[XmlElement(ElementName = "transferstate")]
	public string transferstate { get; set; }
}
```
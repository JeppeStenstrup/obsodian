[[400 Projects]]

# ParameterDiff

For:: [[Vitec Aloc]]
Tags:: [[C Sharp|C#]] [[XML]]
Started:: 2022-07-01
Finished:: 
Status:: #project/ongoing 

[[Xml configs to serialize|Serialized configs]] -- done

Compare `.cfg` against `.master` and compile differences in a template config for each master.

Output format: [[XML]].

```cs:Pseudo:
foreach(var conf in configs)
{
	foreach(var item in conf)
	{
		// make case for nested items
		if item != master.Item { parameterizedConfigObj.Add(master.Item) }
	}
}
```

```dataview
list from [[ParameterDiff]]
sort file desc
```
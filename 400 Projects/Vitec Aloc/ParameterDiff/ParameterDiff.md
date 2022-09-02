[[400 Projects]]

# ParameterDiff

For:: [[Vitec Aloc]]
Tags:: [[C Sharp|C#]] [[XML]]
Started:: 2022-07-01
Finished:: 
Status:: #project/ongoing 

[[Xml configs to serialize|Serialized configs]]

Compare `.cfg` against `.master` and compile differences in a template config for each master.

Output format unknown, might be [[XML]].

```cs:Pseudo:
foreach(var conf in configs)
{
	foreach(var item in conf)
	{
		// make case for nested items
		if item != master.Item { template.Add(master.Item) }
	}
}
```

```dataview
list from [[ParameterDiff]]
```
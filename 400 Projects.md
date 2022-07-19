[[000 Home]]

# 400 Projects

## Ongoing
```dataview
TABLE without id
    link(file.link, title) as "Project",
	For,
	Started
FROM #project/ongoing
WHERE file.name != "000 Home"
SORT Started desc
```

## Finished
```dataview
TABLE without id
    link(file.link, title) as "Project",
	For,
	Finished
FROM #project/finished
WHERE file.name != "000 Home"
LIMIT 10
SORT Started desc
```

## Planned
```dataview
TABLE without id
    link(file.link, title) as "Project",
	For
FROM #project/planned
WHERE file.name != "000 Home"
SORT Started desc
```
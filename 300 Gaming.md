[[000 Home]]

# Gaming
## Playing
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Tags,
	Started
FROM #game/playing
WHERE Started
LIMIT 10
SORT Started desc
```

## Finished
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Tags,
	Started,
	Finished,
	Rating AS "Rating/5"
FROM #game/completed
LIMIT 10
SORT rating DESC
```

## Backlog
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Tags
FROM #game/backlog
WHERE !Started
LIMIT 10
SORT Started desc
```

## Series
```dataview
TABLE without id
    link(file.link, title) + " ("+ length(file.inlinks) +")" as "Series",
	sort(file.inlinks, (link) => link.SeriesOrder) as Backlinks
FROM #game/series
SORT file.inlinks.SeriesOrder
```
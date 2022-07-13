[[000 Home]]

# Gaming
## Playing
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Started,
	Tags
FROM #game/playing
WHERE Started
LIMIT 10
SORT Started desc
```

## Backlog
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Started,
	Tags
FROM #game/backlog
LIMIT 10
SORT SeriesOrder
```

## Finished
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Started,
	Finished,
	Rating + "/5" AS "Rating",
	Tags
FROM #game/completed
LIMIT 10
SORT rating DESC
```

## Series
```dataview
TABLE without id
    link(file.link, title) + " ("+ length(file.inlinks) +")" as "Series",
	sort(file.inlinks, (link) => link.SeriesOrder) as Backlinks
FROM #game/series
SORT file.inlinks.SeriesOrder
```
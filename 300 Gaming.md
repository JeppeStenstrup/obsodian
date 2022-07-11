[[000 Home]]

# Gaming
## Playing
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Started
FROM #game/playing LIMIT 10
SORT Started desc
```

## Finished
```dataview
TABLE without id
    link(file.link, title) as "Game",
	Started,
	Finished,
	Rating AS "Rating/5"
FROM #game/completed LIMIT 10
SORT rating DESC
```

## Series
```dataview
TABLE without id
    link(file.link, title) + " ("+ length(file.inlinks) +")" as "Series",
	file.inlinks as Backlinks
FROM #game/series
SORT rating
```
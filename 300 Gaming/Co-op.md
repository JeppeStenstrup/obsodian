[[300 Gaming]]

Tags:: #game/tag

# Co-op
```dataview
table without id
    link(file.link, title) as "title",
    Publisher,
	Platform,
	Finished,
	Rating,
	Series,
	SeriesOrder
where contains(this.file.inlinks, file.link)
sort Series
```
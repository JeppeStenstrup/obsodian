[[300 Gaming]]

Tags:: <%"#"%>game/series

# <%await tp.file.title%>
```dataview
table without id
    link(file.link, title) as "Game",
    Started,
	Finished,
	Rating
where contains(this.file.inlinks, file.link)
sort SeriesOrder
```
```dataview
table without id
 ("![](" + poster + ")") as Poster,
 file.link as Title,
 year as Year, director as Director,
 "⭐ " + scoreImdb as "⭐ IMDB",
 my-rating as MyRating, 
 genre
from "Movies"
sort year desc
```

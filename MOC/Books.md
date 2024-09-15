```dataview
TABLE WITHOUT ID
	"![|120](" + cover + ")" as Cover,
	link(file.link, title) as Title,
	author as Author,
	publish as Published
from "Books"
SORT publish DESC
```

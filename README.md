# Obsidian-stuff
## What is Obsidian?
Instead of me explaining what [Obsidian](https://obsidian.md) is and how to use it, I suggest you visit [the YouTube channel of Linking Your Thinking](https://www.youtube.com/watch?v=QgbLb6QCK88&list=PL3NaIVgSlAVLHty1-NuvPa9V0b0UwbzBd) and watch a few of those free videos. Alternatively, [the help section of the Obsidian website](https://help.obsidian.md/Start+here) has detailed documentation that is worth a read.

Both resources walk you through the basics of how Obsidian works and what you can expect in the tool and its files. I strongly urge you to go watch those short videos, read the docs, and take notes. 
## Plugins
My goal is to keep things as simple as possible. This is the list of plugins I currently have installed:
- [Templater](https://github.com/SilentVoid13/Templater) - A template plugin for obsidian 
- [DataView](https://github.com/blacksmithgu/obsidian-dataview) - Provides a query language for filtering, sorting, and extracting data from Markdown pages.
- [Sortable](https://github.com/alexandru-dinu/obsidian-sortable) - Makes (Dataview)Tables sortable.
- [Quickadd](https://github.com/chhoumann/quickadd) - QuickAdd is a powerful combination of four tools (called choices): templates, captures, macros, and multis.
- [Various Complements](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin) - This plugin enables you complete words like the auto-completion of IDE.
- [Book Search](https://github.com/anpigon/obsidian-book-search-plugin) - Easily create book notes.

## My setup
I use the tools that I learned from [GRIP](https://gripbook.com/). For me daily notes works very well. During the day I dump all thoughts and stuff I want to remember in a single daily note. Once a week I go through the notes, add some context (so I can find it back at a later time) and archive it.
- [Daily notes](https://help.obsidian.md/Plugins/Daily+notes) - My template: [templates/daily note template.md](templates/daily%20note%20template.md)
- [Weekly review](https://rickpastoor.com/sections/weeklyreview.html) - My template: [templates/weekly review template.md](templates/weekly%20review%20template.md)
- [Quarterly/yearly review](https://rickpastoor.substack.com/p/making-your-goals-happen) - My template: [templates/quarterly review template.md](templates/quarterly%20review%20template.md)

## Second brain
After reading the book of Tiago Forte about [Building a second brain](https://fortelabs.com/blog/basboverview/) it was clear to me that it is way too complex for my use case. I use my notes mainly for personal stuff. Work related projects have their own systems and methods. It is difficult to combine it in one note system. For work I use Obsidian to prepare meetings, make notes during meetings and use it for my personal development at work.
I ended up with a system for personal projects and a few special MOC(Maps of Content) notes for a few things.
- A new project (e.g. booking a trip) is a note in the root folder of my vault. I can easily add stuff and visit the note during the day. When it is finished I archive the projects(note) during my weekly review.
- For some things I use tags to retrieve things at a later point in time. I want to get rid of it and slowly converting stuff to MOC notes

### Books
Most books I read is from an e-reader. I take note on the the e-reader device. Once I finished a book, I create a new note in the folder "Books". To create a book note I use the book search plugin I listed above (You can follow the readme on their github page to install and connect it with the google books API). In the generated note I add all notes from my e-reader. In daily notes I place a mention and the main take away for a book  

### Movies/Documentaries 
I like to store the movies and documentaries I have watched. For each movie I have a seperate note in a "Movie" folder. In my daily notes I can link to these notes and write down some interesting thoughts about the movie. The content of the movie notes are filled automatically. Below a step-by-step instruction of my set-up. Here you can find my datatable script for a nice overview of all your movies -> [MOC/Movies.md](MOC/Movies.md)

- You will need an [OMDb API](http://www.omdbapi.com/) key. You can request one for free [here](http://www.omdbapi.com/apikey.aspx). OMDb is an open movie database which we will use to automatically fetch movie metadata.
- Add the [scripts/movies.js](scripts/movies.js) script to your Obsidian vault, e.g. inside of a /Scripts folder to keep things organized
- Create a new template for a Movie note - My template: [templates/new movie template.md](templates/new%20movie%20template.md)
- Create a macro in QuickAdd. Macros in QuickAdd allow you to automatically run a series of actions in succession. Here we will create a command palette action that runs the macro. The macro will initiate the script you added in Step 1 to automatically fetch movie metadata from OMDb, then create a new note using your template from Step 2.
  - Go to _Obsidian Settings > QuickAdd_
  - Click _Manage Macros_
  - Give your macro a name, e.g. "Lookup Movie"
  - Click _Configure_ on the macro
  - Under _User Scripts_, select "movie" and click _Add_
  - Click the cog icon next to the movie script and enter your OMDb API key
  - Click _Template_
    - Click on the cog next to Untitled Template Choice and choose the Movie template you created
    - Enable File Name Format and use {{VALUE:fileName}} as the file name. The fileName value takes the Title of the movie/show and removes any illegal characters
    - Enter the folder to create movie notes in
  - Close all the popup modals and go back to the _Settings > QuickAdd_ screen
  - In the dropdown next to the _Add Choice_ button choose _Macro_
    - Give your command a name like "Add Movie" then click _Add Choice_
    - Click the cog next to your Add Movie macro and choose the "Lookup Movie" macro you just created
    - Toggle the lightning bolt icon which will make this macro available from your main command palette
- Launch the command palette with CMD + P (or your preferred hotkey); Type "Add Movie" (i.e. the name of your macro command)
  - Enter a movie title; You should see search results from OMDb appear
  - Select the movie of your choice from the results
  - Enter the rating 0-10 and fill where you watched the movie e.g. Netflix, Cinetree
  - You should automatically see a new note open with your template pre-filled

## Always Looking to Improve
Do you have suggestions on how to improve these templates? Want to contribute to the project?
1. Create an issue and let me know.
2. Or submit a pull request to make changes.


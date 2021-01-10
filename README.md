# Notes

A minamlist command-line interface for note taking and organization, journaling, and task-tracking/managment written in ruby inspired by (and emulative of) Max Hodak's note-taking [system](https://github.com/maxhodak/notes) written in python. 

### Installation
1. Clone repo

2. Add the following to your `.bash_profile`: 

```
export NOTESPATH="/path/to/where/you/want/notes/saved"
export NOTESCRIPT="/path/to/where/you/cloned/this/repo"
```
    
3. Run the following commands inside repo:

```
make install
bundle install
```
    
### Basic Usage

```
notes new <note> -- create new note
notes search [-ft] <phrase> --- search notes by name and or contents
notes scratch --- open scratch pad
notes edit <note> --- edit existing note
notes journal --- create/edit daily journal entry
notes [-h] --- show this message
notes [-l | --list] --- show all notes
notes stack [-adlnr] <title> --- create, delete, list, display stacks
notes push [-d] <stack> --- push to stack
notes pop [-d] <stack> <index> --- pop off stack
```
**Create a new note**

```
$ notes new my brilliant idea
```

This will create a new note `$NOTESPATH/year/month/date/my_brilliant_idea.md` and open your default editor.

**Edit an existing note**

```
$ notes edit idea
``` 

If there is only one matching note, it will open it in your default editor. Otherwise, you will see a message like this:

```
Multiple notes found.
----
[0]  2021/01/10/my_brilliant_idea.md
[1]  2020/12/25/ideas.md
----
Choose an index to edit (or 'q' to quit): 
```
**Search notes**
```
$ notes search idea
```
This will show all notes containing 'idea' in their name and all notes in which 'idea' is written. Output will look like this:

```
[0]  2021/01/10/my_brilliant_idea.md
[1]  2020/12/25/ideas.md
[2]  2021/01/07/books.md:- **Essays**, **Ideas and Opinions**, Albert Einstein
[3]  2021/01/07/books.md:*Survey of the philosophizers of the 20th century that prevade modern thinking and contributed to the ideas that have formed my own*
[4]  2021/01/09/dhamma_letter_13.md:Dhamma letter # 13 need idea to to understand. Too theoretical now. 
----
Choose an index to edit (or 'q' to quit):
```

Use `f` to search only note names:

```
$ notes search -f idea
[0]  2021/01/10/my_brilliant_idea.md
[1]  2020/12/25/ideas.md
----
Choose an index to edit (or 'q' to quit):
```

Use `t` to search for mentions only: 

```
$ notes search -t idea
[0]  2021/01/07/books.md:- **Essays**, **Ideas and Opinions**, Albert Einstein
[1]  2021/01/07/books.md:*Survey of the philosophizers of the 20th century that prevade modern thinking and contributed to the ideas that have formed my own*
[2]  2021/01/09/dhamma_letter_13.md:Dhamma letter # 13 need idea to to understand. Too theoretical now. 
----
Choose an index to edit (or 'q' to quit): 
```

### Helpful Aliases

```
alias scratch="notes scratch"
alias journal="notes journal"
alias stack="notes stack"
alias push="notes push"
alias pop="notes pop"
alias search="notes search"
```

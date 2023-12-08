# Package name balderdash

Balderdash is game where an obscure word is selected, and people need to either know or make up a definition for the word. All of the definitions are shared with the group, and people select which they think is the best, or correct, definition of the word. The person whose definition is selected by the most people is the winner. 

Mara Averick had the brilliant idea that we could do this with R package names instead of words! Instead of defining the word, the idea is to describe what the package does.

## Game setup

The game requires: 
* Some kind of polling system, so people can enter and vote on definitions
* Videoconferencing, some kind of Zoom, where you can be together in a virtual meeting (although you could probably do this without being on a call together, it's just more fun if you are)
* A list of package names that you can select from

### Polling software

Some kind of polling software works well for this, where people can type in a response and then it can get upvoted. I use [slido](https://www.slido.com/). 

* Create a new event
* Use the Audience Q&A functionality
* Get the link to the poll, and share the link with people participating

### Videoconferencing software

This can be whatever you usually use

### Package names

We've assembled a list of R package names that are on CRAN. They're in the package-names.csv file in this repository. During the game, you'll use this list to randomly select a package name. 

You can curate this list so that you only have a select set, maybe ones in a particular category, or that are meaningful to your group. 

## Running the game

This is how to run the game once you're all on a virtual call together.

* Share the link to the poll with people
* Select a package name 

```
# Read in the file with the list of package names

library(tidyverse)
package_names <- read_csv("package-names.csv")

# Select a random package

pull(sample_n(package_names, 1)[1])
```


* Have people go to the poll, and in the Q&A, like they're asking a question, type in what they think the package does. Everyone should do this as an Anonymous user, so people don't know who has written what description.
* Wait until you have everyone's responses in
* Give everyone 2 votes - they can upvote 2 of their favorite descriptions
* Whichever package name has the most is the winner!
* Once that winner is selected, the person can identify themselves. 
* The moderator clears all the questions, and then you're ready to go again with a different package. 

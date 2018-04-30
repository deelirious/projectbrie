# Project Brie - Design Document
Use this https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet to guide you on how to write this stuff ^^

## Conventions
+ Images/Art/Pictures = Artwork
+ Piece of Artwork = Fragment


## Description

### Index page

### Fragment game

### Random Artwork game

## Constraints


## Data Handling
This chapter is about the retrieval of data that will be used to filter and retrieve artworks that are able to be displayed to the user.
It also discusses the memory of the application and how the memorized data can be used.

### Getting the artwork
The artwork will be retrieved using the clients website, arteditions.org. When a new artwork is requested the application will send a request to the clients php server with a injected random 4 digit nummer between 1000...2000 acting as the ID of the artwork. 
This is the link we use: http://arteditions.org/scripts/php/getdetail.php?view=artworks&id=*[injection]*
The clients server responds with information about that ID.

**The information retrieved is:**
+ artist name
+ ID
+ number of artworks
+ Artwork[i]
+ price
+ description
+ title
+ type

The application uses the Artwork[i] piece of information inorder to retrieve the artwork. Using this information we can easily inject it into this link http://arteditions.org/@Artwork[i] which gives us the artwork that was requested.

Incase the ID is invalid, AKA contains no information, the application will redo the request. 

### Filtering
Inorder to get the artwork we desire, it is possible to format the request by using the other information such as artist name or the description. The application can redo requests until it finds a matching description to retrieve an artwork fitting the description.
For instance, if the user likes artworks with the description "Love", this can be saved in a cookie and be used to filter through the artworks to retrieve another artwork similar to the artwork that the user liked.

### Fragments
We now know how to retrieve an artwork and how to filter artworks to retrieve a liked artwork. 
But how do we visualize only a part of this artwork, and how do we make sure that the application remembers what artworks we're displaying the user? Hint.. Cookies ^.^, To be continued.....


## MoSCoW Analysis


## Open Questions

# json-documentation

## song.json represents a song

| element         | description                             | type           |
|-----------------|-----------------------------------------|----------------|
|song             |Top level                                |song data object|
|&emsp; title     |Song title                               |string          |
|&emsp; artist    |Song artist                              |string          |
|&emsp; musicians |A list of musicians who play on the song |array of strings|

## menu.json represents a menu in a UI

| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
|menu             |Top level                                |array of menu columns|
|&emsp; header    |The name of the column                   |string               |
|&emsp; items     |A list of menu items in the columns      |array of menu items  |
|&emsp;&emsp; id  |The ID of the menu item                  |string               |
|&emsp;&emsp;label|The label that is displayed in the UI    |string               |

### alternative documentation with seperate tables instead of indentation for nesting
Although this method is harder to read, it is more useful if we have another JSON 
response that uses menu items in a different context, then we could just link to the 
menu items table.

#### menu object: represents a menu
| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
| menu            |Top level                                |array of menu columns|

#### menu column object: represents a column in a menu 
| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
| header          |The name of the column                   |string               |
| items           |A list of menu items in the columns      |array of menu items  |

#### menu item object: represents something you can select in a menu
| element| description                             | type                |
|--------|-----------------------------------------|---------------------|
| id     |The ID of the menu item                  |string               |
| label  |The label that is displayed in the UI    |string               |

## comment.json represents a comment

|element|description|type|required|notes|
|---|---|---|---|---|
|comment|Top level|comment data object|required||
|&emsp; userID|The ID of the user making the comment|string|required||
|&emsp; discussionID|The ID of the discussion that is being commented on|integer|required||
|&emsp; time|The time the comment was posted|string|optional|Time is GMT. Format is YYYY-MM-DD HH:MM:SS Default is the time the comment is recieved by the server.| 
|&emsp; text|The text of the comment|string|required||

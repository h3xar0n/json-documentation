# json-documentation

## song.json represents a song

| element         | description                             | type           | required|
|-----------------|-----------------------------------------|----------------|---------|
|song             |Top level                                |song data object|yes      |
|&nbsp; title     |Song title                               |string          |yes      |
|&nbsp; artist    |Song artist                              |string          |yes      |
|&nbsp; musicians |A list of musicians who play on the song |array of strings|no       |

## menu.json represents a menu in a UI

| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
|menu             |Top level                                |array of menu columns|
|&nbsp; header    |The name of the column                   |string               |
|&nbsp; items     |A list of menu items in the columns      |array of menu items  |
|&nbsp;&nbsp; id  |The ID of the menu item                  |string               |
|&nbsp;&nbsp;label|The label that is displayed in the UI    |string               |

### alternative documentation with seperate tables instead of indentation for nesting
Although this method is harder to read, it is more useful if we have another JSON response that uses menu items in a different context, then we could just link to the menu items table.

| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
|menu             |Top level                                |array of menu columns|

| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
| header          |The name of the column                   |string               |
| items           |A list of menu items in the columns      |array of menu items  |

| element| description                             | type                |
|--------|-----------------------------------------|---------------------|
| id     |The ID of the menu item                  |string               |
| label  |The label that is displayed in the UI    |string               |


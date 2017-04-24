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

## forecast.json represents a one day forecast

| element     | description                             | type    | notes                                                                                |
|-------------|-----------------------------------------|---------|--------------------------------------------------------------------------------------|
| date        | The date of the forecast                | string  | Format is YYYY-MM-DD                                                                 |
| description | The description of the weather          | string  | Can have these values: "sunny","overcast", "partly cloudy", "raining", and "snowing" |
| maxTemp     | The maximum temperature                 | integer | Temperature in degrees Celsius                                                       |
| minTemp     | The minimum temperature                 | integer | Temperature in degrees Celsius                                                       |
| windSpeed   | The speed of the wind                   | integer | Speed in kilometers per hour                                                         |
| danger      | Whether or not the weather is dangerous | Boolean |  

## 3cast.json represents a three day forecast

| element     | description                              | type                      | notes                                                                                |
|-------------|------------------------------------------|---------------------------|--------------------------------------------------------------------------------------|
| longitude   | The longitude of the forecast's location | integer                   |                                                                                      |
| latitude    | The latitude of the forecast's location  | integer                   |                                                                                      |
| forecasts   | Forecasts for three days                 | array of forecast objects |                                                                                      |
| &emsp;date        | The date of the forecast                 | string                    | Format is YYYY-MM-DD                                                                 |
| &emsp;description | The description of the weather           | string                    | Can have these values: "sunny","overcast", "partly cloudy", "raining", and "snowing" |
| &emsp;maxTemp     | The maximum temperature                  | integer                   | Temperature in degrees Celsius                                                       |
| &emsp;minTemp     | The minimum temperature                  | integer                   | Temperature in degrees Celsius                                                       |
| &emsp;windSpeed   | The speed of the wind                    | integer                   | Speed in kilometers per hour                                                         |
| &emsp;danger      | Whether or not the weather is dangerous  | boolean                   |                                                                                      | 

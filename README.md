# json-doc-reformat

## song.json represents a song

```
{
"songs":
  {
    "title": "Secrets",
    "artist": "The Weeknd",
    "musicians":
      [ "Abel Makkonen Tesfaye", "Roland Orzabal", 
        "Curt Smith"]
  }
} 
```

| element         | description                             | type           |
|-----------------|-----------------------------------------|----------------|
|song             |Top level                                |song data object|
|title            |Song title                               |string          |
|artist           |Song artist                              |string          |
|musicians        |A list of musicians who play on the song |array of strings|


## menu.json represents a menu in a UI

```
{
"menu": [ 
  { "header": "File",
    "items": [
      {"id": "Open", "label": "Open"},    
      {"id": "New", "label": "New"},
      {"id": "Close", "label": "Close"}
  ]},
  { "header": "View",
    "items": [
      {"id": "ZoomIn", "label": "Zoom In"},
      {"id": "ZoomOut", "label": "Zoom Out"},
      {"id": "OriginalView", "label": "Original View"}
  ]}
]}
```

| element       | description                             | type                |
|---------------|-----------------------------------------|---------------------|
|menu           |Top level                                |array of menu columns|
|     header    |The name of the column                   |string               |
|     items     |A list of menu items in the columns      |array of menu items  |
|             id|The ID of the menu item                  |string               |
|          label|The label that is displayed in the UI    |string               |

### alternative documentation with seperate tables instead of indentation for nesting

Although this method is harder to read, it is more useful if we have another JSON 
response that uses menu items in a different context. In that case, we could just link to the 
menu items table.

#### menu object: represents a menu

| element         | description                             | type                |
|-----------------|-----------------------------------------|---------------------|
| menu            | Top level                               |array of menu columns|

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

```
{
  "comment": {
    "userID": "aeidelman",
    "discussionID": 964564445654,
    "time": "2017-04-23 4:04:37",
    "text": "Honey, do we need more Hazelnut creamer?"
  }
}
```

| element       | description                                        | type              | required|notes|
|---------------|----------------------------------------------------|-------------------|---------|-----|
| comment       | Top level                                          |comment data object|required |     |
| userID        | The ID of the user making the comment              | string            |required |     |
| discussionID  | The ID of the discussion that is being commented on| integer           |required |     |
| time          | The time the comment was posted                    | string            |optional | Time is GMT. Format is YYYY-MM-DD HH:MM:SS Default is the time the comment is recieved by the server.| 
| text          | The text of the comment                            | string            |required |     |

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

| element   |             | description                              | type                      | notes                                                                                |
|-----------|-------------|------------------------------------------|---------------------------|--------------------------------------------------------------------------------------|
| longitude |             | The longitude of the forecast's location | integer                   |                                                                                      |
| latitude  |             | The latitude of the forecast's location  | integer                   |                                                                                      |
| forecasts |             | Forecasts for three days                 | array of forecast objects |                                                                                      |
|           | date        | The date of the forecast                 | string                    | Format is YYYY-MM-DD                                                                 |
|           | description | The description of the weather           | string                    | Can have these values: "sunny","overcast", "partly cloudy", "raining", and "snowing" |
|           | maxTemp     | The maximum temperature                  | integer                   | Temperature in degrees Celsius                                                       |
|           | minTemp     | The minimum temperature                  | integer                   | Temperature in degrees Celsius                                                       |
|           | windSpeed   | The speed of the wind                    | integer                   | Speed in kilometers per hour                                                         |
|           | danger      | Whether or not the weather is dangerous  | boolean                   |                                                                                      |

## meeting.json represents a scheduled meeting

| element |             | description                                                     | type                | required | notes                                                                   |
|---------|-------------|-----------------------------------------------------------------|---------------------|----------|-------------------------------------------------------------------------|
| meeting |             | Top level                                                       | meeting data object | required |                                                                         |
|         | time        | The time of the meeting                                         | string              | required | Time is GMT. Format is YYYY-MM-DD HH:MM                                 |
|         | duration    | The duration of the meeting                                     | integer             | required | Duration is in minutes                                                  |
|         | description | The description of the meeting                                  | string              | required |                                                                         |
|         | location    | The location of the meeting                                     | string              | optional | Default is an empty string.                                             |
|         | reminder    | A reminder to notify participants of the meeting                | integer             | optional | Measured in minutes. Default is 10 minutes.                             |
|         | invitees    | A list of the email addresses of people invited to the meetings | array of strings    | optional | The strings should be valid email addresses. Default is an empty array. |

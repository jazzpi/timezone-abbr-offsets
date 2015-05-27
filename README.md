# timezone-abbr-offsets

Timezone abbreviations mapped to offsets from UTC in minutes. May return unexpected results for ambiguous abbreviations.

## Example

```js
var timezones = require('timezone-abbr-offsets')
console.log(timezones.CEST) // -> 120
console.log(timezones.UYST) // -> -120
console.log(timezones.X) // -> -660
```

## Explanation

This is a simple object with the timezone abbreviations from [Wikipedia](http://en.wikipedia.org/wiki/List_of_time_zone_abbreviations) and one-character military timezones from http://timeanddate.com. When timezone abbreviations are ambiguous, the timezone that had more searches on Google Trends is used (like [this](http://www.google.com/trends/explore#q=bangladesh%20standard%20time%2C%20bougainville%20standard%20time%2C%20british%20summer%20time&cmpt=q&tz=)). There were two cases where Google Trends couldn't help:

 - CST: Stands for Central Standard Time in Australia and North America. This is mapped to UTC-06:00 (i.e. `-360`)
 - FKST: Stands for Lord Howe Standard Time and Lord Howe Summer Time. Google Trends didn't have enough search volume to make a comparison, so this is mapped to UTC+10:30 (i.e. `630`)

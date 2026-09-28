# Weather icon options

Use these icon values when matching sky-condition text:

| Icon name | Sky text matched |
| --- | --- |
| `thunderstorm` | thunder, storm, lightning |
| `rainy` | rain, shower, drizzle |
| `ac_unit` | snow, sleet, ice, freezing; also clear temperatures below 30°F |
| `foggy` | fog, mist, haze |
| `partly_cloudy_day` | partly, mostly sunny, few clouds |
| `cloud` | cloud, overcast |
| `sunny` | sun, clear, bright |
| `emergency_heat` | clear/non-cloudy temperatures above 90°F |
| `help` | unknown or blank conditions |

## Weather icon colors

Weather icon colors are assigned inline by `weatherIcon.style.color` in
`index.html`. To change a condition's color, update its entry in the
`weatherIconColor()` mapping. A regular CSS `color` rule for a weather icon
class will not override that inline style, so changing or adding a CSS class
color alone will have no visible effect.

## Night icon timing

Frame mode gets sunrise and sunset from NOAA's annual solar table through an
HTTP GET and scrapes the current day's row. Update `APEX_ZIP_CENTROID` and
`APEX_TIME_ZONE` in `index.html` together if the display location changes. If
the page request or scrape fails, night mode falls back to 10 p.m.–6 a.m.
NOAA returns HTML rather than a stable JSON contract, so update
`noaaTableAfterHeading()` or `noaaTableMinutes()` if its page layout changes.

## DC Rawhides Line Dances

This repo reads from a google spreadsheet, and formats the data to be easier to read.

[Source Spreadsheet](https://docs.google.com/spreadsheets/d/1-l36tKe7PT3P1iYVJ4H7WpYfG5t0yXXTuH6wlFBbegY/edit#gid=0)

[Formatted Webpage](http://caseywatts.com/dcrawhides-linedances)

## Technical background

## Technology Used
This project is written in vanilla javascript (using ES6 things like `await` and `fetch`) and vanilla CSS (using CSS3 things like `var()`). This is deployed to github pages.

### Using Google Sheets as a backend

The easiest way I found to connect to a Google Spreadsheet using vanilla JS in the browser is to use the [Google Data API](https://developers.google.com/gdata/docs/directory
) for it, as described in [this handy article](https://coderwall.com/p/duapqq/use-a-google-spreadsheet-as-your-json-backend)

Our URL using this api is:
https://spreadsheets.google.com/feeds/list/1-l36tKe7PT3P1iYVJ4H7WpYfG5t0yXXTuH6wlFBbegY/od6/public/values?alt=json  

The Google Data API is sorta deprecated - but their newer "Sheets API v4" still doesn't have an unauthenticated way to access this (even for a public spreadsheet). (as of 4/2019)

#### Alternative APIs
A public spreadsheet *can* be accessed as a CSV, but that's a little harder to parse than getting the JSON directly. If the Google Spreadsheets Data API gets turned off, we should investigate the Sheets API again (hopefully it supports this by then), or we may want to consume it as a "publish to web" CSV instead

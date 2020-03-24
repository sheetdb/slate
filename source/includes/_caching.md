# Caching

## How do we cache your data

By default, we cache your API data for 30 seconds. If you are on paid plan you can change this period in API settings up to 7 days. Caching guarantees the fastest response time, especially for a large number of requests.

When cache is enabled, changes to the spreadsheet are not reflected in the API's until the cache expires, or until you make changes to the spreadsheet using SheetDB API. There is also an endpoint to reset cache in API settings.

**Example:**

- If you have cache enabled for 7 days and one day later you change the content in the Google Spreadsheet website, for the next 6 days, GET endpoint will return **the old data!** You can use purge endpoint to manually reset the cache.

- If you modify a spreadsheet using SheetDB API - for example with the POST request, the cache will be cleared for you and after the change your GET requests will return new content immediately.

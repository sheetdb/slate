# Other

## Value Render Option

To your GET (get and search) requests, you can add optional `mode` parameter. It controls how values should be rendered in the output, as described in the following:

`FORMATTED_VALUE` (default) - Values will be calculated & formatted in the reply according to the cell's formatting. Formatting is based on the spreadsheet's locale, not the requesting user's locale. For example, if A1 is 1.23 and A2 is =A1 and formatted as currency, then A2 would return "$1.23".

`UNFORMATTED_VALUE` - Values will be calculated, but not formatted in the reply. For example, if A1 is 1.23 and A2 is =A1 and formatted as currency, then A2 would return the number 1.23.

`FORMULA` - Values will not be calculated. The reply will include the formulas. For example, if A1 is 1.23 and A2 is =A1 and formatted as currency, then A2 would return "=A1".

## Value Input Option

To your POST, PUT and PATCH (create and update) requests, you can add optional `mode` parameter. It controls whether input strings are parsed or not, as described in the following:

`USER_ENTERED` (default) - The input is parsed exactly as if it were entered into the Google Sheets UI, so "Mar 1 2016" becomes a date, and "=1+2" becomes a formula. Formats may also be inferred, so "$100.15" becomes a number with currency formatting.

`RAW` - The input is not parsed and is simply inserted as a string, so the input "=1+2" places the string "=1+2" in the cell, not a formula. (Non-string values like booleans or numbers are always handled as RAW.)

<aside class="notice">
If you want to search for formula values, use the RAW mode.
</aside>

<aside class="notice">
<strong>Warning:</strong> If you use RAW for updating, other formulas in the row will be converted to strings.
</aside>

## Authentication

You can add HTTP Basic Auth to each API as an additional security for your API's. You can enable it on the API Settings tab.

You will receive a *login* and *password*. You have to send it for every request that has basic authentication enabled. If the credentials are incorrect API will respond with error `401 Unauthorized`.

## API Limits

After you hit your rate limit, your requests will return an error: `429 Too Many Requests`. You can check limits at our <a href="https://sheetdb.io/pricing">pricing page</a>.

There are 2 more limits:

- 2,000 requests per user (for 100 seconds)
- variable limit of requests per one spreadsheet (for 100 seconds)

Both are limits imposed by Google and cannot be changed. If you need more, best solution is enabling cache. SheetDB limit will be calculated as usual, however Google limits do not apply because in the case of cache results we do not query Google servers. In this case remember to set the cache for longer than you plan to poll this request.

**Make the first request before a larger batch to prepare the cache.**

## Caching

By default, we cache your API data for 30 seconds. If you are on paid plan you can change this period in API settings up to 7 days. Caching guarantees the fastest response time, especially for a large number of requests.

When cache is enabled, changes to the spreadsheet are not reflected in the API's until the cache expires, or until you make changes to the spreadsheet using SheetDB API. There is also an endpoint to reset cache in API settings.

**Example:**

- If you have cache enabled for 7 days and one day later you change the content in the Google Spreadsheet website, for the next 6 days, GET endpoint will return **the old data!** You can use purge endpoint to manually reset the cache.

- If you modify a spreadsheet using SheetDB API - for example with the POST request, the cache will be cleared for you and after the change your GET requests will return new content immediately.

## Data safety

The confidentiality of your data is very important to us, which is why we do not store any of your data on our servers, other than API data for caching reasons. Also, for people without an API URL, guessing is almost impossible, but if you still need more protection, you can enable [Basic Auth](#authentication).

We use the best tools and services available to protect your data.

### What does SheetDB have access to?

SheetDB can only access spreadsheets for which the API has been created. This means that SheetDB do not have access to your other files.


## We are here for you!

If you have any questions please feel free to ask via
<a href="#" class=""
   data-name="support"
   data-domain="sheetdb"
   data-tld="io"
   onclick="window.location.href = 'mailto:' + this.dataset.name + '@' + this.dataset.domain + '.' + this.dataset.tld; return false;">email</a>
or inapp chat.

<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />

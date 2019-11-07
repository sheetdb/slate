# Other

## Value Input Option

To your POST, PUT and PATCH (create and update) requests, you can add optional `mode` parameter. It controls whether input strings are parsed or not, as described in the following:

`RAW` (default) - The input is not parsed and is simply inserted as a string, so the input "=1+2" places the string "=1+2" in the cell, not a formula. (Non-string values like booleans or numbers are always handled as RAW.)

`USER_ENTERED` - The input is parsed exactly as if it were entered into the Google Sheets UI, so "Mar 1 2016" becomes a date, and "=1+2" becomes a formula. Formats may also be inferred, so "$100.15" becomes a number with currency formatting.

## Authentication

You can add HTTP Basic Auth to each API as an additional security for your API's. You can enable it on the API Settings tab.

You will receive a *login* and *password*. You have to send it for every request that has basic authentication enabled. If the credentials are incorrect API will respond with error `401 Unauthorized`.

## API Rate Limits

After you hit your rate limit, your requests will recive `429 Too Many Requests`. You can check limits in <a href="https://sheetdb.io/pricing">pricing page</a>.

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

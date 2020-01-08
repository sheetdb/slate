# Data safety

## How we protect your data

The confidentiality of your data is very important to us, which is why we do not store any of your data on our servers, other than API data for caching reasons. Also, for people without an API URL, guessing is almost impossible, but if you still need more protection, you can enable [Basic Auth](#authentication).

We use the best tools and services on the market to protect your data.

## What does SheetDB have access to?

SheetDB can only access spreadsheets for which the API has been created. This means that SheetDB do not have access to your other files.

If you need more details, we have permission to:

* https://www.googleapis.com/auth/userinfo.email
* https://www.googleapis.com/auth/userinfo.profile
* https://www.googleapis.com/auth/spreadsheets

We do not have permission to:

* https://www.googleapis.com/auth/drive

Without the last permission, it is impossible to list your files = to access to them.

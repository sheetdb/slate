# SheetDB API

## GET - All data

```shell
# Get all data
curl https://sheetdb.io/api/v1/58f61be4dda40

# Get 10 results starting from 20
curl https://sheetdb.io/api/v1/58f61be4dda40?limit=10&offset=20

# Get all data sorted by name in ascending order
curl https://sheetdb.io/api/v1/58f61be4dda40?sort_by=name&sort_order=asc
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    // Get all data
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40')
    .then( response => {
        console.log(response.data);
    });

    // Get 10 results starting from 20
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?limit=10&offset=20')
    .then( response => {
        console.log(response.data);
    });

    // Get all data sorted by name in ascending order
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?sort_by=name&sort_order=asc')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
[
  {
    "id": "1",
    "name": "Tom",
    "age": "41"
  },
  {
    "id": "2",
    "name": "Alex",
    "age": "24"
  },
  {
    "id": "3",
    "name": "John",
    "age": "51"
  }
]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40`

Returns an array with all data from the spreadsheet.

You can use optional parameters:

* `limit` - the number of rows that should be returned
* `offset` - row from which it should start (how many rows to skip)
* `sort_by` - the column you want to sort by
* `sort_order` - sort in `asc` or `desc` order
* `sort_method` - if you want to search by date, use `sort_method=date`, it will automatically detect the date format

## GET - Keys

```shell
# Get keys
curl https://sheetdb.io/api/v1/58f61be4dda40/keys
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/keys', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/keys')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
["id", "name", "age", "comment"]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/keys`

Returns an array with all keys from the spreadsheet = values of the first row of the document.

## GET - Document name

```shell
# Get the document name
curl https://sheetdb.io/api/v1/58f61be4dda40/name
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/name', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/name')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "name": "SheetDB test document"
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/name`

Returns the name of the document.

## GET - List of available sheets

```shell
curl https://sheetdb.io/api/v1/58f61be4dda40/sheets
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/sheets', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/sheets')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "sheets": [
    "Sheet1",
    "Sheet2"
  ]
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/sheets`

Returns a list of all available sheets (tabs).

## GET - Count

```shell
curl https://sheetdb.io/api/v1/58f61be4dda40/count
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/count', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/count')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "rows": 5
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/count`

Returns the number of rows in the document (without first row).

## GET - Search in document

```shell
curl https://sheetdb.io/api/v1/58f61be4dda40/search?name=Steve&age=22&casesensitive=true
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/search?name=Steve&age=22&casesensitive=true', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/search?name=Steve&age=22&casesensitive=true')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
[
  {
    "id": "61",
    "name": "Steve",
    "age": "22",
    "comment": "special"
  }
]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/search?name=Steve&age=22&casesensitive=true`

Returns an array of all rows matching parameters. If any query fails, the result **will NOT** be listed. If you want to check if any parameter is true, check out <a href="#get-search-or-in-document"># GET - Search OR</a>

You can search using wildcards. Asteriks (`*`) can represent any string.
Wildcard work only when READ and SEARCH permissions are both enabled, if only SEARCH peremission is enabled, wildcard will not work for security reasons.

If you want to search for a string with a space, just repace space with `%20`

You can use optional parameters:

* `limit` - the number of rows that should be returned
* `offset` - row from which it should start (how many rows to skip)
* `sort_by` - the column you want to sort by
* `sort_order` - sort in `asc` or `desc` order
* `sort_method` - if you want to search by date, use `sort_method=date`, it will automatically detect the date format
* `casesensitive` - by default search is not case sensitive, to make it case sensitive set this parameter to `true`

## GET - Search OR in document

```shell
curl https://sheetdb.io/api/v1/58f61be4dda40/search_or?name=Steve&age=19&casesensitive=true
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/search_or?name=Steve&age=19&casesensitive=true', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/search_or?name=Steve&age=19&casesensitive=true')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
[
  {
    "id": "61",
    "name": "Steve",
    "age": "22",
    "comment": "special"
  },
  {
    "id": "422",
    "name": "James",
    "age": "19"
  }
]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/search_or?name=Steve&age=19&casesensitive=true`

Similar to <a href="#get-search-in-document"># GET - Search</a> but if **any parameter** succeed to match, it will be listed in response.

You can search using wildcards. Asteriks `*` can represent any string.
Wildcard work only when READ and SEARCH permissions are both enabled, if only SEARCH peremission is enabled, wildcard will not work for security reasons.

If you want to search for a string with a space, just repace space with `%20`

You can use optional parameters:

* `limit` - the number of rows that should be returned
* `offset` - row from which it should start (how many rows to skip)
* `sort_by` - the column you want to sort by
* `sort_order` - sort in `asc` or `desc` order
* `sort_method` - if you want to search by date, use `sort_method=date`, it will automatically detect the date format
* `casesensitive` - by default search is not case sensitive, to make it case sensitive set this parameter to `true`

## POST - Create row

```shell
curl -X POST -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40 -d '{"data":[{ "name": "Scott", "age": "25" }]}'
```

```php
<?php
$data = http_build_query(
    [
        'data' =>
        [
          ['name' => 'Scott', 'age' => 25]
        ]
    ]
);

$options = array(
  'http' => array(
    'method'  => 'POST',
    'header'  => 'Content-type: application/x-www-form-urlencoded',
    'content' => $data
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.post('https://sheetdb.io/api/v1/58f61be4dda40',{
        "data": {"name": "Scott", "age": 25}
    }).then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "created": 1
}
```

`POST https://sheetdb.io/api/v1/58f61be4dda40`

Create rows in document. Your request should contain `data` parameter - it should be an array of rows. Keys inside the object should be a column names (see <a href="#get-keys"># GET - keys</a>) and values will be values inside a spreadsheet. Rows will be added at the end of spreadsheet. If you want to add a single row, simply send an array with one item `{data: [{"id":5,"name":"Frank"}]})`.

You can use value `INCREMENT` (upper case). SheetDB will look for the biggest number in the given column and increase by 1.

API will return the number of created rows with status code `201 Created`.

## PATCH/PUT - update

```shell
curl -X PATCH -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/id/61 -d '{"data":[{ "name": "Scott", "age": "25" }]}'
```

```php
<?php
$data = http_build_query(
    [
        'data' =>
            [
              ['name' => 'Scott', 'age' => 25]
            ]
    ]
);

$options = array(
  'http' => array(
    'method'  => 'PATCH',
    'header'  => 'Content-type: application/x-www-form-urlencoded',
    'content' => $data
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/id/61', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.patch('https://sheetdb.io/api/v1/58f61be4dda40/id/61',{
        "data": {"name": "Scott", "age": 25}
    }).then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "updated": 1
}
```

`PATCH/PUT https://sheetdb.io/api/v1/58f61be4dda40/{column}/{value}`

<aside class="notice">
Replace <code>{column}</code> and <code>{value}</code> with your values (without braces). Ex. https://sheetdb.io/api/v1/58f61be4dda40/id/61
</aside>

Update row(s) for given column and value. Similar to <a href="#get-search"># GET - Search</a> you must specify a key (column name) and value to find. Any rows that match the condition will be updated.

`PATCH` requests will update only values passed in data object.

`PUT` requests will update entire row - some fields might get emptied.

It returns count of updated rows.

## PATCH/PUT - Batch update

```shell
curl -X PATCH -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/batch_update -d '{"data":[{"query":"id=1", "name":"Mathew", "age":20},{"query":"id=2", "age":25}]}'
```

```php
<?php
$data = http_build_query(
[
    'data' =>
    [
        ['query' => 'id=1', 'name' => 'Mathew', 'age' => 20],
        ['query' => 'id=2', 'age' => 25],
    ]
]);

$options = array(
  'http' => array(
    'method'  => 'PATCH',
    'header'  => 'Content-type: application/x-www-form-urlencoded',
    'content' => $data
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/batch_update', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.patch('https://sheetdb.io/api/v1/58f61be4dda40/batch_update', {
        data: [
            {
                "query":"id=1",
                "name":"qwes",
                "age":20
            },
            {
                "query":"id=2",
                "age":25,
            }
        ]
    }).then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
  "updated": 2
}
```

`PATCH/PUT https://sheetdb.io/api/v1/batch_update`

<aside class="notice">
Batch update works only on paid accounts.
</aside>

Update for various queries. You have to add an `data` param to your request. Each object in it should have a `query` key with the actual query (for example, "id=5"), and the remaining keys will be updated, as in a regular PATCH / PUT request. Here is an example of the `data` parameter in the body of the request:

<code>
[
  {
    "query":"id=1",
    "name":"Mathew",
    "age":20
  },
  {
    "query":"id=2",
    "age":25,
  }
]
</code>

`PATCH` requests will update only values passed in data object.

`PUT` requests will update entire row - some fields might get emptied.

It returns count of updated rows.

## DELETE

```shell
curl -X DELETE -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/id/61'
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'DELETE'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/id/61', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.delete('https://sheetdb.io/api/v1/58f61be4dda40/id/61')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
    "deleted": 1
}
```

`DELETE https://sheetdb.io/api/v1/58f61be4dda40/{column}/{value}`

<aside class="notice">
Replace <code>{column}</code> and <code>{value}</code> with your values (without braces). Ex. https://sheetdb.io/api/v1/58f61be4dda40/id/61
</aside>

Delete row(s) for given column and value. Similar to <a href="#get-search"># GET - Search</a> you must specify a key (column name) and value to find. Any rows that match the condition will be deleted.

It returns count of deleted rows.

## DELETE - All content

```shell
curl -X DELETE -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/all
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'DELETE'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/all', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.delete('https://sheetdb.io/api/v1/58f61be4dda40/all')
    .then( response => {
        console.log(response.data);
    });
</script>
```

> Example response:

```json
{
    "deleted": 5
}
```

`DELETE https://sheetdb.io/api/v1/58f61be4dda40/all`

Delete all rows without the first one (column names) in spreadsheet. By default first sheet (tab) is selected but you can target any sheet you want using param sheet. Example: `?sheet=Sheet2`

It returns count of deleted rows.


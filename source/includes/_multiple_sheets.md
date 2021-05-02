# Multiple Sheets (tabs)

To select other then the first sheet you need to pass a <code style="word-break:normal;">sheet</code> parameter wtih sheet name. You can add this parameter to any of our RESTful requests (`GET`, `POST`, `PATCH`, `PUT`, `DELETE`).

When sheet is not found you'll get 404 error.

Here are sample URLs for different methods (for a sheet named `sheet2`):

- `GET` <small>https://sheetdb.io/api/v1/58f61be4dda40?sheet=sheet2</small>
- `POST` <small>https://sheetdb.io/api/v1/58f61be4dda40?sheet=sheet2</small>
- `PATCH` <small>https://sheetdb.io/api/v1/58f61be4dda40/{column}/{value}?sheet=sheet2</small>
- `DELETE` <small>https://sheetdb.io/api/v1/58f61be4dda40/{column}/{value}?sheet=sheet2</small>

## GET - All data from a tab

```shell
# Get all data from "Sheet2"
curl https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2

# You can still use limit, offset and sort parameters
curl https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2&limit=10&offset=20
```

```php
<?php
// define options
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    // Get all data
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2')
    .then( response => {
        console.log(response.data);
    });

    // You can still use limit, offset and sort parameters
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2&limit=10&offset=20')
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

// Sheet "Sheet2"
client.read({ sheet: "Sheet2" }).then(function(data) {
  console.log(data);
}, function(err){
  console.log(err);
});
```

> Example response:

```json
[
  {
    "player": "Smith",
    "score": "41"
  },
  {
    "player": "Martha",
    "score": "43"
  },
  {
    "player": "Craig",
    "score": "12"
  },
  {
    "player": "Michael",
    "score": "61"
  }
]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40?sheet=Sheet2`

This is an example how to get data from sheet `Sheet2`

## POST - Add a sheet to the spreadsheet (tab)

```shell
curl -X POST -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/sheet -d '{"name": "New Sheet", "first_row":["id","name"]}'
```

```php
<?php
$data = http_build_query(
  [
    'name' => "New Sheet",
    'first_row' => ["id","name"]
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
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/sheet', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.post('https://sheetdb.io/api/v1/58f61be4dda40/sheet',{"name": "New Sheet", "first_row":["id","name"]})
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
// our Node.js library does not support this method
```

> Example response:

```json
{
  "created":1
}
```

`POST https://sheetdb.io/api/v1/58f61be4dda40/sheet`

<aside class="notice">
Tabs requests works only on plans premium and above.
</aside>

Creates a new sheet (tab) in the spreadsheet. 2 params are required:

* `name` - the name of the new sheet
* `first_row` - first row of spreadsheet that contain an array with column names. For example: `["id","name","score"]`

## DELETE - Delete a sheet (tab)

```shell
curl -X DELETE -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/sheet -d '{"name":"New Sheet"}'
```

```php
<?php
$data = http_build_query(
  [
    'name' => "New Sheet"
  ]
);

$options = array(
  'http' => array(
    'method'  => 'DELETE',
    'header'  => 'Content-type: application/x-www-form-urlencoded',
    'content' => $data
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/sheet', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.delete('https://sheetdb.io/api/v1/58f61be4dda40/sheet',{
        "data":{
            "name":"New Sheet"
        }
    })
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
// our Node.js library does not support this method
```

> Example response:

```json
{
  "deleted": 1
}
```

`DELETE https://sheetdb.io/api/v1/58f61be4dda40/sheet`

<aside class="notice">
Tabs requests works only on paid plans premium and above.
</aside>

Deletes a sheet (tab) and the content. Requires one param:

* `name` - the name of the sheet you want to delete

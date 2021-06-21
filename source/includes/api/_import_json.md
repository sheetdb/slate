## POST - Import JSON

```shell
curl -X POST -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/import/json -d '{"json":[{ "name": "Scott", "age": "25" }]}'
```

```php
<?php
$data = http_build_query(
    [
        'json' =>
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
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/import/json', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.post('https://sheetdb.io/api/v1/58f61be4dda40/import/json',{
        "json": {"name": "Scott", "age": 25}
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

`POST https://sheetdb.io/api/v1/58f61be4dda40/import/json`

If you have empty spreadsheet without the first row you can use this endpoint to import entire JSON. Make sure that the spreadsheet is empty, if not the endpoint will append new content with the first row. First row (coumn names) will be generated from the first object in array.

Required parameters:

* `json` - should contain valid json array, e.g. `[{ "name": "Scott", "age": "25" }]`

Optional parameters:

* `sheet` - to select other then the first sheet

API will return the number of created rows with status code `201 Created`.

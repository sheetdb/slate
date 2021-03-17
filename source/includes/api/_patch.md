## PATCH/PUT - Update

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

Requests will update only values passed in data object.

It returns count of updated rows.

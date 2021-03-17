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

`PATCH/PUT https://sheetdb.io/api/v1/58f61be4dda40/batch_update`

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

Requests will update only values passed in data object.

It returns count of updated rows.

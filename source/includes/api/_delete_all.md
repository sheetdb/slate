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

## DELETE - Duplicates

```shell
curl -X DELETE -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/duplicates
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'DELETE'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/duplicates', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.delete('https://sheetdb.io/api/v1/58f61be4dda40/duplicates')
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
    "duplicates": 3
}
```

`DELETE https://sheetdb.io/api/v1/58f61be4dda40/duplicates`

Deletes all duplicate rows, all columns must contain exactly the same data to be deleted.

By default first sheet (tab) is selected but you can target any sheet you want using param sheet. Example: `?sheet=Sheet2`

It returns count of duplicated rows.

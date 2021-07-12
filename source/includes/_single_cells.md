# Single cells

## GET - Cells values

```shell
# Get A1 cell
curl https://sheetdb.io/api/v1/58f61be4dda40/cells/A1
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/cells/A1', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/cells/A1')
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
// we do not support single cells in our node package :(
```

> Example response:

```json
{
    "A1":"id"
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/cells/A1`

If you want to retrieve the contents of a single cell using coordinates like A1, B10 etc. you can use this endpoint. Returns an array with coordinates as key and cell contents as value.

If you want to get multiple cells just separate them with a comma. Example:

`GET https://sheetdb.io/api/v1/58f61be4dda40/cells/A1,A2,B5`

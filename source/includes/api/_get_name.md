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

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

client.endpoint('name').then(function(data) {
    console.log(data);
}, function(error){
    console.log(error);
});
```

> Example response:

```json
{
  "name": "SheetDB test document"
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/name`

Returns the name of the document.

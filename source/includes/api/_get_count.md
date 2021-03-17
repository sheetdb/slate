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

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

client.endpoint('count').then(function(data) {
    console.log(data);
}, function(error){
    console.log(error);
});
```

> Example response:

```json
{
  "rows": 5
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/count`

Returns the number of rows in the document (without first row).

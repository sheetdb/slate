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

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

client.endpoint('keys').then(function(data) {
    console.log(data);
}, function(error){
    console.log(error);
});
```

> Example response:

```json
["id", "name", "age", "comment"]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/keys`

Returns an array with all keys from the spreadsheet = values of the first row of the document.

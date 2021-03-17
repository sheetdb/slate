## GET - List of available sheets

```shell
curl https://sheetdb.io/api/v1/58f61be4dda40/sheets
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/sheets', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40/sheets')
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

client.endpoint('sheets').then(function(data) {
    console.log(data);
}, function(error){
    console.log(error);
});
```

> Example response:

```json
{
  "sheets": [
    "Sheet1",
    "Sheet2"
  ]
}
```

`GET https://sheetdb.io/api/v1/58f61be4dda40/sheets`

Returns a list of all available sheets (tabs).

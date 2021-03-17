## DELETE

```shell
curl -X DELETE -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40/id/61'
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'DELETE'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40/id/61', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.delete('https://sheetdb.io/api/v1/58f61be4dda40/id/61')
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

// Delete all rows where 'name' equals 'Smith'
client.delete(
  'id', // column name
  '1' // value to search for
).then(function(data) {
  console.log(data);
}, function(err){
  console.log(err);
});
```

> Example response:

```json
{
    "deleted": 1
}
```

`DELETE https://sheetdb.io/api/v1/58f61be4dda40/{column}/{value}`

<aside class="notice">
Replace <code>{column}</code> and <code>{value}</code> with your values (without braces). Ex. https://sheetdb.io/api/v1/58f61be4dda40/id/61
</aside>

Delete row(s) for given column and value. Similar to <a href="#get-search"># GET - Search</a> you must specify a key (column name) and value to find. Any rows that match the condition will be deleted.

It returns count of deleted rows.

You can use optional parameters:

* `limit` - the number of rows to delete. When dealing with a large spreadsheet and a large number of rows to delete, is's recommended to use limit.

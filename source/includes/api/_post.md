## POST - Create row

```shell
curl -X POST -H "Content-Type: application/json" https://sheetdb.io/api/v1/58f61be4dda40 -d '{"data":[{ "name": "Scott", "age": "25" }]}'
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
    'method'  => 'POST',
    'header'  => 'Content-type: application/x-www-form-urlencoded',
    'content' => $data
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    axios.post('https://sheetdb.io/api/v1/58f61be4dda40',{
        "data": {"name": "Scott", "age": 25}
    }).then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

// Adds single row
client.create({ name: "William", age: 25 }).then(function(data) {
  console.log(data);
}, function(err){
  console.log(err);
});

/// Adds bunch of rows
rows = [
  { name: "William", age: 25 },
  { name: "Jayden", age: 25 }
]
client.create(rows).then(function(data) {
  console.log(data);
}, function(err){
  console.log(err);
});
```

> Example response:

```json
{
  "created": 1
}
```

`POST https://sheetdb.io/api/v1/58f61be4dda40`

Create rows in document. Your request should contain `data` parameter - it should be an array of rows. Keys inside the object should be a column names (see <a href="#get-keys"># GET - keys</a>) and values will be values inside a spreadsheet. Rows will be added at the end of spreadsheet. If you want to add a single row, simply send an array with one item `{"data": [{"id":5,"name":"Frank"}]}`.

You can also add multiple rows at once using an array of objects. Example: `{"data": [{"id":5,"name":"Frank"},{"id":6,"name":"Marc"}]}`

You can use value `INCREMENT` (upper case). SheetDB will look for the biggest number in the given column and increase by 1.

API will return the number of created rows with status code `201 Created`.

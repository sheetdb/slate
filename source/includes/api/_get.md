## GET - All data

```shell
# Get all data
curl https://sheetdb.io/api/v1/58f61be4dda40

# Get 10 results starting from 20
curl https://sheetdb.io/api/v1/58f61be4dda40?limit=10&offset=20

# Get all data sorted by name in ascending order
curl https://sheetdb.io/api/v1/58f61be4dda40?sort_by=name&sort_order=asc
```

```php
<?php
$options = array(
  'http' => array(
    'method'  => 'GET'
  )
);

$result = json_decode(
  file_get_contents('https://sheetdb.io/api/v1/58f61be4dda40', false, stream_context_create($options))
);
```

```html--javascript
<script src="//cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.js"></script>
<script>
    // Get all data
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40')
    .then( response => {
        console.log(response.data);
    });

    // Get 10 results starting from 20
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?limit=10&offset=20')
    .then( response => {
        console.log(response.data);
    });

    // Get all data sorted by name in ascending order
    axios.get('https://sheetdb.io/api/v1/58f61be4dda40?sort_by=name&sort_order=asc')
    .then( response => {
        console.log(response.data);
    });
</script>
```

```javascript--node
const sheetdb = require("sheetdb-node");
const client = sheetdb({ address: '58f61be4dda40' });

// Read whole spreadsheet
client.read().then(function(data) {
    console.log(data);
}, function(error){
    console.log(error);
});

// Read first two rows from sheet "Sheet2"
client.read({ limit: 2, sheet: "Sheet2" }).then(function(data) {
  console.log(data);
}, function(err){
  console.log(err);
});
```

> Example response:

```json
[
  {
    "id": "1",
    "name": "Tom",
    "age": "41"
  },
  {
    "id": "2",
    "name": "Alex",
    "age": "24"
  },
  {
    "id": "3",
    "name": "John",
    "age": "51"
  }
]
```

`GET https://sheetdb.io/api/v1/58f61be4dda40`

Returns an array with all data from the spreadsheet.

You can use optional parameters:

* `limit` - the number of rows that should be returned
* `offset` - row from which it should start (how many rows to skip)
* `sort_by` - the column you want to sort by
* `sort_order` - sort in `asc` or `desc` order
* `sort_method` - if you want to sort by date, set this parameter to `date`, it will automatically detect the date format
* `cast_numbers` - if you want to cast the value to a number, add column names separated by commas. Example: [https://sheetdb.io/api/v1/58f61be4dda40?cast_numbers=id,age](https://sheetdb.io/api/v1/58f61be4dda40?cast_numbers=id,age)
* `single_object` - if you want to get ony one item as an object (not in the array), set this parameter to `true`

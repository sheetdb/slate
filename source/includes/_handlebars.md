# Our handlebars snippet

## Handlebars Installation

Copy the following code and add it before the closing `</body>` tag.

`<script src="https://sheetdb.io/scripts/sheetdb-handlebars-1.0.6.js"></script>`

That's it. You are ready to use our handlebars snippet.

## Display data

Now you can display data from your spreadsheet.

1. Add `data-sheetdb-url="SHEETDB_API_URL"` to the parent element. For example <div>
2. Add handlebars `{{` and `}}` and fill them with the column name you want to display.

### Optional parameters

```html
<table>
  <thead>
    <tr>
      <td>ID</td>
      <td>Name</td>
      <td>Age</td>
      <td>Comment</td>
    </tr>
  </thead>
  <tbody data-sheetdb-url="https://sheetdb.io/api/v1/58f61be4dda40"
         data-sheetdb-sort-by="age"
         data-sheetdb-sort-order="desc">
    <tr>
      <td>{{id}}</td>
      <td>{{name}}</td>
      <td>{{age}}</td>
      <td>{{comment}}</td>
    </tr>
  </tbody>
</table>
<script src="https://sheetdb.io/scripts/sheetdb-handlebars-1.0.6.js"></script>
```

* By default, you will receive data from the first sheet (tab). If you want to work with another sheet, use `data-sheetdb-sheet` and enter the name of the sheet (case sensitive).
* You can limit and offset your response using `data-sheetdb-limit` and `data-sheetdb-offset` attributes
* You can search for specific data in your sheet using `data-sheetdb-search` attribute. If you want to use more than one condition join them using & symbol. Example: `data-sheetdb-search="name=Tom&age=15"`
* You can sort the response using `data-sheetdb-sort-by` attribute - it should be a name of the column you want to sort by. You can alo specify the order using `data-sheetdb-sort-order` - (desc or asc)

<aside class="notice">
If you are using Vue.js, you have to use <code>v-pre</code> attribute on elements that contain our snippets, like following: <code>&#60;div v-pre>{{name}}&#60;/div></code>
</aside>

### Here is the result of right hand code:

<table>
  <thead>
    <tr>
      <td>ID</td>
      <td>Name</td>
      <td>Age</td>
      <td>Comment</td>
    </tr>
  </thead>
  <tbody data-sheetdb-url="https://sheetdb.io/api/v1/58f61be4dda40"
         data-sheetdb-sort-by="age"
         data-sheetdb-sort-order="desc">
    <tr>
      <td>{{id}}</td>
      <td>{{name}}</td>
      <td>{{age}}</td>
      <td>{{comment}}</td>
    </tr>
  </tbody>
</table>
<script src="https://sheetdb.io/scripts/sheetdb-handlebars-1.0.6.js"></script>

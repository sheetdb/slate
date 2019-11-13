---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL
  - php: PHP
  - html--javascript: JavaScript

toc_footers:
  - <a href='https://sheetdb.io'>SheetDB</a>
  - <a href='https://sheetdb.io/apis'>Dashboard</a>

includes:
  - errors
  - restful_api
  - multiple_sheets
  - handlebars
  - other

search: true
---

# Introduction

Each spreadsheet document you want to access must be configured in the SheetDB panel as an API. After creating the API, you'll receive a unique http address. You can send RESTful requests to read, create, update or delete rows. The rest of the documentation explains how each request works and what you will receive in response.

You can choose your preferred programming language in the upper right corner.

* Shell - the command line
* PHP - examples in pure PHP, you can also use [our composer library](https://github.com/sheetdb/sheetdb-php)
* JavaScript - we recommend to use Axios library or [our npm library](https://github.com/sheetdb/sheetdb-js)
* Pure HTML - to learn how to use SheetDB with only HTML <a href="#handlebars-installation">go to Handlebars</a>

# Installation

No configuration needed. As long as you can send HTTP requests and use the JSON format, you're good to go!

You can also use one of our Libraries.

WordPress plugin: [SheetDB on WordPress](https://wordpress.org/plugins/sheetdb/)
JavaScript: [Google Spreadsheet API for JavaScript on GitHub](https://github.com/sheetdb/sheetdb-js)<br />
PHP: [Google Spreadsheet API for PHP on GitHub](https://github.com/sheetdb/sheetdb-php)

# Example spreadsheet

You can play with our test API here: [https://sheetdb.io/api/v1/58f61be4dda40](https://sheetdb.io/api/v1/58f61be4dda40)

You can also visit Google Sheets document here: [google docs test document](https://docs.google.com/spreadsheets/d/1mrsgBk4IAdSs8Ask5H1z3bWYDlPTKplDIU_FzyktrGk/edit).

<aside class="notice">The test spreadsheet resets every hour.</aside>

First row of your spreadsheet should contain the column names. Each next row will be treated as a record (according to naming from first row).

Our Example spreadsheet looks like this:

| id | name | age | comment |
|---|---|---|---|
| 1 | Tom | 41 |  |
| 2 | Alex | 24 |  |
| 3 | John | 51 |  |
| 61 | Steve | 22 | special |
| 422 | James | 19 |  |

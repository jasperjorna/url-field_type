## Usage[](#usage)

This section will show you how to use the field type via API and in the view layer.


### Setting Values[](#usage/setting-values)

You can set the URL field type value with a string.

    $entry->example = "http://pyrocms.com";


### Basic Output[](#usage/basic-output)

The URL field type returns the string value:

    $entry->example; // http://pyrocms.com


### Presenter Output[](#usage/presenter-output)

This section will show you how to use the decorated value provided by the `\Anomaly\UrlFieldType\UrlFieldTypePresenter` class.


#### UrlFieldTypePresenter::query()[](#usage/presenter-output/urlfieldtypepresenter-query)

The `query` field type return the URL query string as an array. An optional `key` can be passed to return a specific value.

###### Returns: `array` or `string` or `null`

###### Arguments

<table class="table table-bordered table-striped">

<thead>

<tr>

<th>Key</th>

<th>Required</th>

<th>Type</th>

<th>Default</th>

<th>Description</th>

</tr>

</thead>

<tbody>

<tr>

<td>

$key

</td>

<td>

false

</td>

<td>

string

</td>

<td>

null

</td>

<td>

The the query key value to return.

</td>

</tr>

</tbody>

</table>

###### Example

    $id = $decorated->query('id');

###### Twig

    ID: {{ decorated.query('id') }}


#### UrlFieldTypePresenter::parsed()[](#usage/presenter-output/urlfieldtypepresenter-parsed)

The `parsed` method returns the parsed URL.

###### Returns: `array` or `string` or `null`

###### Arguments

<table class="table table-bordered table-striped">

<thead>

<tr>

<th>Key</th>

<th>Required</th>

<th>Type</th>

<th>Default</th>

<th>Description</th>

</tr>

</thead>

<tbody>

<tr>

<td>

$key

</td>

<td>

false

</td>

<td>

string

</td>

<td>

null

</td>

<td>

The the key value to return.

</td>

</tr>

</tbody>

</table>

###### Example

    $host = $decorated->parsed('host');

###### Twig

    {{ decorated.parsed('host') }}


#### UrlFieldTypePresenter::link()[](#usage/presenter-output/urlfieldtypepresenter-link)

The `link` method returns an HTML link.

###### Returns: `string`

###### Arguments

<table class="table table-bordered table-striped">

<thead>

<tr>

<th>Key</th>

<th>Required</th>

<th>Type</th>

<th>Default</th>

<th>Description</th>

</tr>

</thead>

<tbody>

<tr>

<td>

$title

</td>

<td>

false

</td>

<td>

string

</td>

<td>

The URL

</td>

<td>

The title of the link.

</td>

</tr>

<tr>

<td>

$attributes

</td>

<td>

false

</td>

<td>

array

</td>

<td>

null

</td>

<td>

The an associated array of the link attribute values.

</td>

</tr>

</tbody>

</table>

###### Example

    $decorated->link('PyroCMS');

###### Twig

    {{ decorated.link('PyroCMS')|raw }}


#### UrlFieldTypePresenter::to()[](#usage/presenter-output/urlfieldtypepresenter-to)

The `to` method returns a URL to the provided path using the value as a root URL.

###### Returns: `string`

###### Arguments

<table class="table table-bordered table-striped">

<thead>

<tr>

<th>Key</th>

<th>Required</th>

<th>Type</th>

<th>Default</th>

<th>Description</th>

</tr>

</thead>

<tbody>

<tr>

<td>

$path

</td>

<td>

false

</td>

<td>

string

</td>

<td>

null

</td>

<td>

The URI path to append to the URL.

</td>

</tr>

</tbody>

</table>

###### Example

    $decorated->to('docs'); // http://pyrocms.com/docs


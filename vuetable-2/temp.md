### # fields
- type: _Array_
- default: _none_
- required: _true_
- description

  Array of field definition that Vuetable will be used to map to the data structure in order to render the table for presentation.

### # api-url
- type: _String_
- default: `''` _(empty string)_
- description

  The URL of the api endpoint that Vuetable will interact with. If the API supports sorting, filtering, pagination of the data, 
  Vuetable can automatically append appropriate information to the server via query string.
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # api-mode
- type: _Boolean_
- default: `true`
- description

  By default, Vuetable will load the data from and send the request to the API endpoint specified in `api-url`. If you prefer to 
  supply your own data instead of automatically requesting the data from server, you have to set `api-mode` to `false`. Then, pass 
  the data via `data` prop.

  Please not that disabling `api-mode` (by setting it to `false`) will also **disable** pagination, sorting, and filtering functions.

  > __Note__  
  > Setting `api-mode` to `false` is not recommended. It will not scale well when you have to handle a large dataset
  > yourself instead of letting database manager handles it for you. This functionality is provided to 

### # data
- type: _Array_
- default: `null`
- description

  The data that Vuetable will be used to render the table when `api-mode` is set to `false`.

  > __Note__  
  > The prop only works when `api-mode` is `false`.

### # load-on-start
- type: _Boolean_
- default: `true`
- required: _true_
- description

  Whether Vuetable should immediately load the data from the server. 

  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # data-path
- type: _String_
- default: `data`
- description
  
  The path inside the data structure that actually contains the data. If the data is at the root of the structure, set 
  this prop to empty string, e.g. `data-path=""`.
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # pagination-path 
- type: _String_
- default: `links.pagination`
- description

  The pagination path inside the data structure that contains the pagination information. If the your data from the server
  does not have pagination information, you should set the prop to empty string, e.g. `pagination-path=""`, to suppress
  Vuetable warning.
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # query-params
- type: _Object_
- default: 
  ```
  {
    sort: 'sort',
    page: 'page',
    perPage: 'per_page'
  }
  ```
- description

  The text to be used as keys in query string that will be sent to the server. If your API endpoint uses different keys, you can 
  specified them via this prop.
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

  See also: [Sorting, Paging, and Page Sizing of Data](#)
  
### # append-params
- type: _Object_
- default: `{}` _(empty object)_
- description

  Additional parameters that Vuetable should append to the query string when requesting data from the server. 
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

  See also: [Appending Other Parameters to the Query String](#)


### # http-options
- type: _Object_
- default: `{}` _(empty object)_
- description

  Allow passing additional options to the server during AJAX call. Internally, Vuetable uses [`axios`](https://github.com/mzabriskie/axios)
  to handle AJAX request.
  
  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # per-page
- type: _Number_
- default: `10`
- description

  The number of data to be requested per page.

  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # sort-order
- type: _Array_
- default: `[]` _(empty array)_
- description

  The default sort order that Vuetable should use when requesting the data from server.

  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # multi-sort
- type: _Boolean_
- default: `false`
- description

  Enable multiple sort columns interaction.

  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # multi-sort-key
- type: _String_
- default: `alt`
- possible values: `alt`, `ctrl`, `shift`, `meta`
- description

  The key to trigger sort colum adding/subtracting when multi-sort is enabled.

  > __Note__  
  > The prop only works when `api-mode` is `true`.

### # row-class
- type: _String_, _Function_
- default: `''` _(empty string)_
- description

  The CSS class name that will be applied to each table row. 
  
  If `row-class` prop refers to a method, Vuetable will automatically call the given method on each row, passing the row data
  and row index to it. Vuetable will then use the returned string from the given method as CSS class for that row.
  
### # detail-row-component
- type: _String_
- default: `''` _(empty string)_
- description

  A component name to be used as the content of detail row to be displayed underneath the current row.

### # detail-row-transition
- type: _String_
- default: `''` _(empty string)_
- description

  The CSS class to apply to detail row during transition.

### # track-by
- type: _String_
- default: `id`
- description

  The key that uses to unqiuely identified each row in the data array to help track the state of detail row and checkbox 
  features of Vuetable. This is necessary for the detail row and checkbox features to function correctly.
  
  For detail row feature, whenever the user click to expand the detail row, Vuetable will insert the `id` of that row into
  its internal array (`visibleDetailRows`). And when that detail row is hidden, the `id` of that detail row is removed from
  the array.
  
  For checkbox feature, when the user select (checked) a row, Vuetable will insert the `id` of the row into its internal 
  array (`selectedTo`). And when that row is unselected (unchecked), the `id` of that row is removed from the array.
  
  See also: [`visibleDetailRows`](#), and [`selectedTo`](#)

### # css
- type: _Object_
- default: 
  ```
  {
    tableClass: 'ui blue selectable celled stackable attached table',
    loadingClass: 'loading',
    ascendingIcon: 'blue chevron up icon',
    descendingIcon: 'blue chevron down icon',
    detailRowClass: 'vuetable-detail-row',
    sortHandleIcon: 'grey sidebar icon'
  }
  ```
- description

  description here

### # min-rows
- type: _Number_
- default: `0`
- description

  description here


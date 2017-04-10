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
  > `api-url` only works when `api-mode` is `true`.

### # api-mode
- type: _Boolean_
- default: `true`
- description

  By default, Vuetable will load the data from and send the request to the API endpoint specified in `api-url`. If you prefer to 
  supply your own data instead of automatically requesting the data from server, you have to set `api-mode` to `false`. Then, pass 
  the data via `data` prop.
  
  > Please note that 

### # data
- type: _Array_
- default: `null`

description here

### # load-on-start
- type: _Boolean_
- default: `true`
- required: _true_

description here

### # data-path
- type: _String_
- default: `data`

description here

### # pagination-path
- type: _String_
- default: `links.pagination`

description here

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

description here

### # append-params
- type: _Object_
- default: `{}` _(empty object)_

description here

### # http-options
- type: _Object_
- default: `{}` _(empty object)_

description here

### # per-page
- type: _Number_
- default: `10`

description here

### # sort-order
- type: _Array_
- default: `[]` _(empty array)_

description here

### # multi-sort
- type: _Boolean_
- default: `false`

description here

### # multi-sort-key
- type: _String_
- default: `alt`
- possible values: `alt`, `ctrl`, `shift`, `meta`

description here

### # row-class-callback
- type: _String_, _Function_
- default: `''` _(empty string)_

description here

### # detail-row-component
- type: _String_
- default: `''` _(empty string)_

description here

### # detail-row-transition
- type: _String_
- default: `''` _(empty string)_

description here

### # track-by
- type: _String_
- default: `id`

description here

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
description here

### # min-rows
- type: _Number_
- default: `0`

description here


##find

Find all instances of the model matched by filter from the data source.

**Definition**

    GET /locations

**Arguments**

Pass the arguments as the value of the `find` HTTP query parameter, as follows

    /modelName?filter=[filterType1]=<val1>&filter[filterType2]=<val2>...

where *filterType1*, *filterType2*, and so on, are the filter types, and *val1*, *val2* are the corresponding
values, as described in the following table.

The following table describes filter types.

<table>
<thead><tr>
<th>Filter type</th>
<th>Type</th>
<th>Description</th>
</tr></thead>
<tbody>
<tr>
<td>where</td>
<td>Object</td>
<td>Search criteria. Format: <code>{key: val}</code> or <code>{key: {op: val}}</code>  
<p>Operations:</p>
<ul>
<li>gt: &gt;</li>
<li>gte: &gt;=</li>
<li>lt: &lt;</li>
<li>lte: &lt;=</li>
<li>between</li>
<li>inq: IN</li>
<li>nin: NOT IN</li>
<li>neq: !=</li>
<li>like: LIKE</li>
<li>nlike: NOT LIKE</li>
</ul>
</td>
</tr>
<tr>
<td>include</td>
<td>String, Object, or Array</td>
<td>Allows you to load relations of several objects and optimize numbers of requests.
<p>Format:</p>
<ul>
<li><code>posts</code>: Load posts</li>
<li><code>[posts, passports']</code>: Load posts and passports.</li>
<li>{owner: posts}</code>: Load owner and owner's posts.</li>
<li><code>{owner: [posts, passports]}</code>: Load owner, owner's posts, and owner's passports.</li>
<li><code>{owner: [{posts: images}, passports]}</code>: Load owner, owner's posts, owner's posts' images, and owner's passports.</li>
</ul>
</td>
</tr>
<tr>
<td>order</td>
<td>String</td>
<td>Sort order.  Format: 'key1 ASC, key2 DESC' where ASC specifies ascending and DESC specifies descending order.</td>
</tr>
<tr>
<td>limit</td>
<td>Number</td>
<td>Maximum number of instances to return.</td>
</tr>
<tr>
<td>skip (offset)</td>
<td>Number</td>
<td>Skip specified number of instances.  Use offset as alternative.</td>
</tr>
<tr>
<td>fields</td>
<td>Object, Array, or String</td>
<td>The included/excluded fields:
<ul>
<li>
[<code>foo</code>] or <code>'foo'</code> - include only the foo property.</li>
<li>
[<code>foo</code>, <code>bar</code>] - include the foo and bar properties</li>
<li>
<code>{foo: true}</code> - include only foo</li>
<li>
<code>{bat: false}</code> - include all properties, exclude bat</li>
</ul>
</td>
</tr>
</tbody>
</table>

For example,

 - '/weapons': Weapons
 - '/weapons?filter[limit]=2&filter[offset]=5': Paginated Weapons
 - '/weapons?filter[where][name]=M1911': Weapons with name M1911
 - '/weapons?filter[where][audibleRange][lt]=10': Weapons with audioRange < 10
 - '/weapons?filter[fields][name]=1&filter[fields][effectiveRange]=1': Only name and effective ranges
 - '/weapons?filter[where][effectiveRange][gt]=900&filter[limit]=3': The top 3 weapons with a range over 900 meters
 - '/weapons?filter[order]=audibleRange%20DESC&filter[limit]=3': The loudest 3 weapons

 - '/locations': Locations
 - '/locations?filter[where][geo][near]=153.536,-28.1&filter[limit]=3': The 3 closest locations to a given geo point


**Example**

Request:

Find without filter:

    curl http://localhost:3000/locations

Find with a filter:

    curl http://localhost:3000/locations?filter%5Blimit%5D=2

**Note**: For curl, `[` needs to be encoded as `%5B`, and `]` as `%5D`.

Response:

    [
      {
        "id": "87",
        "street": "7153 East Thomas Road",
        "city": "Scottsdale",
        "zipcode": 85251,
        "name": "Phoenix Equipment Rentals",
        "geo": {
          "lat": 33.48034450000001,
          "lng": -111.9271738
        }
      },
      {
        "id": "88",
        "street": "390 Lang Road",
        "city": "Burlingame",
        "zipcode": 94010,
        "name": "Bay Area Firearms",
        "geo": {
          "lat": 37.5874391,
          "lng": -122.3381437
        }
      }
    ]

**Errors**

None


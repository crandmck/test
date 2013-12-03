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

| Filter type  | Type | Description |
| ------------- | ------------- | ---------------|
| where   | Object   | Search criteria. Format: `{key: val}` or `{key: {op: val}}`  Operations: |
| include    | String, Object, or Array   | Allows you to load relations of several objects and optimize numbers of requests. |
| order |  String | Sort order.  Format: 'key1 ASC, key2 DESC' where ASC specifies ascending and DESC specifies descending order. |
|limit| Number | Maximum number of instances to return. |
|skip (offset) | Number | Skip specified number of instances.  Use offset as alternative. |
|fields| Object, Array, or String |  The included/excluded fields:


Fields:
  - `['foo']` or `'foo'` - include only the foo property
  - `['foo', 'bar']` - include the foo and bar properties
  - `{foo: true}` - include only foo
  - `{bat: false}` - include all properties, exclude bat

Operations:
- gt: >
- gte: >=
- lt: <
- lte: <=
- between
- inq: IN
- nin: NOT IN
- neq: !=
- like: LIKE
- nlike: NOT LIKE

Include format
 Format:
 - 'posts': Load posts
 - ['posts', 'passports']: Load posts and passports
 - {'owner': 'posts'}: Load owner and owner's posts
 - {'owner': ['posts', 'passports']}: Load owner, owner's posts, and owner's passports
 - {'owner': [{posts: 'images'}, 'passports']}: Load owner, owner's posts, owner's posts' images, and owner's passports
  
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


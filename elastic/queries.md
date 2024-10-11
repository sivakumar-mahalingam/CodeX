# Create Index

```
PUT /my-index
```

# Add a document to my-index
```
POST /my-index/_doc
{
    "id": "park_rocky-mountain",
    "title": "Rocky Mountain",
    "description": "Bisected north to south by the Continental Divide, this portion of the Rockies has ecosystems varying from over 150 riparian lakes to montane and subalpine forests to treeless alpine tundra."
}
```

# Perform a search in my-index
```
GET /my-index/_search?q="rocky mountain"
```

# Match Query
Search for documents that match a specific term
```
{
  "query": {
    "match": {
      "field_name": "search_term"
    }
  }
}
```

# Multi-Match Query
Search across multiple fields
```
{
  "query": {
    "multi_match": {
      "query": "search_term",
      "fields": ["field1", "field2", "field3"]
    }
  }
}
```

# Range Query
Find documents within a specific range of values
```
{
  "query": {
    "range": {
      "field_name": {
        "gte": "value1",
        "lte": "value2"
      }
    }
  }
}
```

# Term Query
Search for an exact match of a term
```
{
  "query": {
    "term": {
      "field_name": "exact_value"
    }
  }
}
```

# Terms Query
Find documents with any of the terms listed
```
{
  "query": {
    "terms": {
      "field_name": ["value1", "value2", "value3"]
    }
  }
}
```

# Match Phrase Query
Search for an exact phrase within a field
```
{
  "query": {
    "match_phrase": {
      "field_name": "exact phrase"
    }
  }
}
```

# Wildcard Query
Use wildcard characters (* and ?) to search
```
{
  "query": {
    "wildcard": {
      "field_name": "val*"
    }
  }
}
```

# Fuzzy Query
Find similar terms based on a fuzziness level
```
{
  "query": {
    "fuzzy": {
      "field_name": {
        "value": "term",
        "fuzziness": 2
      }
    }
  }
}
```

# Term Aggregation
Group documents by specific field values
```
{
  "aggs": {
    "group_by_field": {
      "terms": {
        "field": "field_name"
      }
    }
  }
}
```

# Nested Query
Search for values within nested objects
```
{
  "query": {
    "nested": {
      "path": "nested_field",
      "query": {
        "bool": {
          "must": [
            { "match": { "nested_field.field_name": "value" } }
          ]
        }
      }
    }
  }
}
```

# Exists Query
Find documents where a field has a value
```
{
  "query": {
    "exists": {
      "field": "field_name"
    }
  }
}
```

# Geo Distance Query
Find documents within a specific distance
```
{
  "query": {
    "geo_distance": {
      "distance": "200km",
      "location": {
        "lat": 40,
        "lon": -70
      }
    }
  }
}
```


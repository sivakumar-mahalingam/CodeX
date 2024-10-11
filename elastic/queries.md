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

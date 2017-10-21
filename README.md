# honeybee-js
Honeybee JSON schema

This is the schema for minimum implementation of honeybee objects.
You can create the objects by using `fromJson` classmethod.

## Analysis Recipe
This is what Honeybee needs to create the analysis and execute it!

### SolarAccessRecipeGridBased
```js
{
  "id": 0, // do NOT overwrite this id
  "hoys": [], // list of hours of the year
  "surfaces": [], // list of honeybee surfaces
  "analysis_grids": [] // list of analysis grids
}
```

### PointInTimeGridBased
```js
{
  "id": 1, // do NOT overwrite this id
  "sky": null, // a honeybee sky
  "surfaces": [], // list of honeybee surfaces
  "analysis_grids": [] // list of analysis grids
  "analysis_type": 0 // [0] illuminance(lux), [1] radiation (kwh), [2] luminance (Candela).
}
```

## Geometry
### HBSurface
```js
{"name": "",
"vertices": [
    [[x, y, z], [x1, y1, z1], [x2, y2, z2]],
    [[x, y, z], [x1, y1, z1], [x2, y2, z2], [x3, y3, z3]], ...],
"surface_type": null  // 0: wall, 5: window
}
```

## Sky
### CIESky
```js
{
  "location": {}, // honeybee (or actually ladybug location schema)
  "day": 1, // an integer between 1-31
  "month": 1, // an integer between 1-12
  "hour": 12.0, // a float number between 0-23
  "north": 0, // degree for north if not Y axis
  "sky_type": 0 // A number between 0-5 --  0: sunny sky
}
```

## Location data
### Location
```js
{
  "city": "",
  "latitude": 0,
  "longitude": 0,
  "time_zone": 0,
  "elevation": 0
}
```

## Analysis grid

### AnalysisPoint
```js
{
  "location": [x, y, z],
  "direction": [a, b, c]
},
```

### AnalysisGrid
```js
{
  "analysis_points": [
    {"location": [x, y, z], "direction": [a, b, c]},
    {"location": [x, y, z], "direction": [a, b, c]},
    {"location": [x, y, z], "direction": [a, b, c]},
    // ...
  ]
}
```

# Map viewer
## UI buttons
- Search 🔎:
- Upload file 📁:
- Paste from clipboard 📄:
- Projection controls 🗺️:
- Polygon editor ✏️:
- Layer selector:
- Layer controls:
- Geolocation: Attempts to geolocate the user.

## URL queries
```
https://angeci.github.io/map/?<queries>
```

- `q`: General searching.
- `utm`: UTM coordinates.
- `mgrs`: Military Grid Reference System (MGRS) coordinates.
- `plus`: Plus Code.
- `mdh`: Maidenhead Locator System (MLS).
- `gh`: Geohash.
- `osm`: OpenStreetMap short URL format.
- `hk1980`: HK1980 grid coordinates.
- `twd67`: TWD67 grid coordinates.
- `twd97`: TWD97 grid coordinates.

### UTM coordinates
Format: UTM zone + easting + northing
```
https://angeci.github.io/map/?utm=50Q+209108+2485039
```

### MGRS coordinates
- 100000 km grid:
```
https://angeci.github.io/map/?mgrs=51QTF
```
- 10 m grid:
```
https://angeci.github.io/map/?mgrs=37QED+8562+6913
```

### Plus Code
- Global Plus Code:
```
https://angeci.github.io/map/?plus=7PXM93MQ+V8
```
- “4+x” local Plus Code, relative to the current map centre:
```
https://angeci.github.io/map/?plus=MM89+6V
```
- Local Plus Code, with locality specified:
```
https://angeci.github.io/map/?plus=MM89+6V+JP-13
```

### Maidenhead Locator System
Can support up to 10 digits “extended subsquares” precision.
```
https://angeci.github.io/map/?mdh=OL72ck71
```

### Geohash
```
https://angeci.github.io/map/?gh=wt0rjmk6
```

### OpenStreetMap short URL format
```
https://angeci.github.io/map/?osm=7QEy3mFcb
```

### HK1980 grid coordinates
Northing first, then easting.
```
https://angeci.github.io/map/?hk1980=823764,837329
```

### TWD67 grid coordinates
```
https://angeci.github.io/map/?twd67=317321,2785079
```

### TWD97 grid coordinates
```
https://angeci.github.io/map/?twd97=318149,2784873
```

### Direct GPS coordinate (WGS84) specification
```
https://angeci.github.io/map/#39.90647,116.39125
```

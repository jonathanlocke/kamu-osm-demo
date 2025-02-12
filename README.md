
# Kamu Demo with OpenStreetMap (OSM) Data

## 0. Install kamu-cli

Execute this command to install the Kamu CLI tool:

`curl -s "https://get.kamu.dev" | sh`

## 1. Download [new-mexico-latest.osm.pbf](https://download.geofabrik.de/north-america/us/new-mexico-latest.osm.pbf)

## 2. Convert the file to CSV format with [osm-pbf-to-csv](https://github.com/jonathanlocke/osm-pbf-to-csv)

## 3. Download OSM GPS probe traces in CSV format with [osm-gpx-to-csv](https://github.com/jonathanlocke/osm-gpx-to-csv)

## 4. Arrange the CSV files from the previous steps in a subfolder called "new-mexico" like this:

```
.
└── new-mexico/
    ├── albuquerque/
    │   └── traces.csv
    ├── nodes.csv
    ├── tags.csv
    └── ways.csv
```

## 5. `kamu init`

## 6. `kamu add *.yaml`

## 7. `kamu pull --all`


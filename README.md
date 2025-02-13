
# Kamu Demo with OpenStreetMap (OSM) Data

## 0. Install kamu-cli

Execute this command to install the Kamu CLI tool:

`curl -s "https://get.kamu.dev" | sh`

## 1. Download Data

Download OSM data for [New Mexico](https://drive.google.com/drive/u/0/folders/1a44geavf3hGfOTNSdbUc0jDm21woe5Xl)

```
.
└── new-mexico/
    ├── albuquerque/
    │   └── traces.csv
    ├── nodes.csv
    ├── tags.csv
    └── ways.csv
```

## 2. `kamu init`

This creates a Kamu workspace.

```
Initialized an empty workspace
```

## 3. `kamu add *.yaml`

This adds datasets to Kamu for OSM nodes, ways and tags in the state of New Mexico, 
as well as GPS traces in the Albuquerque area. The `.yaml` files define where to get
the data, how to read it and how to preprocess it before adding it to Kamu.

```
Added: albuquerque-gps-traces
Added: new-mexico-nodes
Added: new-mexico-tags
Added: new-mexico-ways
Added 4 dataset(s)
```

## 4. `kamu pull --all`

This command pulls the actual data into Kamu:

```
  [7/7] Committed new block 951b954a (new-mexico-nodes)
  [7/7] Committed new block d129d251 (albuquerque-gps-traces)
  [7/7] Committed new block 7ca5c7bd (new-mexico-ways)
  [7/7] Committed new block 09fb16bb (new-mexico-tags)
4 dataset(s) updated
```

## 5. `kamu list`

And now we can see the records in Kamu:

```
┌────────────────────────┬──────┬───────────────┬────────────┬────────────┐
│          Name          │ Kind │    Pulled     │  Records   │    Size    │
├────────────────────────┼──────┼───────────────┼────────────┼────────────┤
│ albuquerque-gps-traces │ Root │ 2 minutes ago │     50,000 │ 539.16 KiB │
│ new-mexico-nodes       │ Root │ 2 minutes ago │ 18,854,040 │ 297.40 MiB │
│ new-mexico-tags        │ Root │ 2 minutes ago │  4,834,683 │  47.98 MiB │
│ new-mexico-ways        │ Root │ 2 minutes ago │ 21,121,744 │ 342.09 MiB │
└────────────────────────┴──────┴───────────────┴────────────┴────────────┘
```
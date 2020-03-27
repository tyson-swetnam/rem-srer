# Data Access

All derived project data for the Ecostate Mapping are hosted on the [CyVerse](https://cyverse.org) data store. Data can be accessed via a variety of web and cloud based mechanisms: HTTPS, 3rd Party Apps, or iRODS command line. 

[Data Store Guide](https://learning.cyverse.org/projects/data_store_guide/en/latest/index.html)

### HTTPS WebDav

CyVerse operates a full [WebDav](http://www.webdav.org/) for HTTPS downloads of data.

This command in a terminal would download the entire directory:

```
wget -r -np -R "index.html*" https://data.cyverse.org/dav-anon/iplant/projects/aes/srer/suas/2019/ecostate_mapping/
```

or 

```
wget --recursive --no-parent -R "index.html*" https://data.cyverse.org/dav-anon/iplant/projects/aes/srer/suas/2019/ecostate_mapping/
```

[WebDav access](https://data.cyverse.org/dav-anon/iplant/projects/aes/srer/suas/2019/ecostate_mapping/)

### Data Commons

The data are also visible from the CyVerse [Data Commons](https://datacommons.cyverse.org), metadata for the data are apparent there.

[Ecostate Mapping HTML access](https://datacommons.cyverse.org/browse/iplant/home/shared/aes/srer/suas/2019/ecostate_mapping)

### 3rd Party Apps

[CyberDuck](https://cyberduck.io) is a 3rd party application for downloading data. You can connect to CyVerse with a [CyVerse Profile](https://learning.cyverse.org/projects/data_store_guide/en/latest/step1.html)

### iRODS

CyVerse Data Store uses [iRODS](https://irods.org)

iRODS path: `/iplant/home/shared/aes/srer/suas/2019/ecostate_mapping`

[Install iCommands](https://learning.cyverse.org/projects/data_store_guide/en/latest/step2.html)

Download the directory:

```
iget -KPTbvrf /iplant/home/shared/aes/srer/suas/2019/ecostate_mapping
```

Download a subset of the data:

```
iget -KPTbvrf /iplant/home/shared/aes/srer/suas/2019/ecostate_mapping/pointclouds/may/15_2_highdensity.laz
```

# Raw and Processed Data 

Data are stored in a file hierarchy around four different parent directories:

(1) `ept` -- [Entwine Point Tile](https://entwine.io) is a cloud native point cloud format which can be queried dynamically using [PDAL](https://pdal.io)

(2) `images` -- the original \*.jpeg imagery

(3) `pointclouds` -- high density SfM point clouds generated from Agisoft Metashape, stored as \*.laz format.

(4) `products` -- Orthophotography and digital surface models generated from the point clouds, stored as \*.tiff GeoTiff format

```
ecostate_mapping/
├── ept
│   ├── may
│   |   ├── plot1
│   |   ├── ...
│   |   └── plotn
│   ├── neon_2019
│   └── sept
│       ├── plot1
│       ├── ...
│       └── plotn
├── images
│   ├── may
│   |   ├── plot1
│   |   ├── ...
│   |   └── plotn
│   └── sept
│       ├── plot1
│       ├── ...
│       └── plotn
├── pointclouds
│   ├── may
│   |   ├── plot1
│   |   ├── ...
│   |   └── plotn
│   └── sept
│       ├── plot1
│       ├── ...
│       └── plotn
└── products
    ├── may
    |   ├── plot1
    |   ├── ...
    |   └── plotn
    └── sept
        ├── plot1
        ├── ...
        └── plotn
```

# Flight and Camera metadata characteristics

| Field | Value |
|-------|-------|
| Aircraft | DJI Phantom 4 RTK |
| Sensor | 20 mpx RGB Global Shutter |
| Aperture & Shutter | Automatic |
| Image format | Jpeg; ~8 mb; 8 bit |
| Autopilot | DJI GS RTK |
| Acquisition Pattern | Single Grid at Nadir, Double Grid at 30° Oblique | 
| Image forward & side overlap | 80% |
| Flying Height | 38 m above ground |
| Flying Speed | 3 m/s |
| Flying time/ha | ~10 min |
| Ground Sample Distance | 1 cm |
| No. of Flight Plots | 53 |
| Plot Sizes | 1.6 – 7.1 ha |
| Images/Plot | 278 – 1563 |
| No. Images/ha | ~200 |
| Total Raw Imagery Size | 341 GB |
| Total Image Product Size | 561 GB |
| Total Area Imaged | 193.1 ha |
| No. of Flying Days | 12 |


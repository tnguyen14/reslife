---
title: Contributions Guide
---

# How to contribute
These floor plans are created in SVG file format to allow for infinite scalability. They are developed using [InkScape](http://www.inkscape.org/), a free and open-source cross-platform software for editing SVG files. In order to work on these files, it is recommended to use InkScape. Other vector graphics editor, such as Illustrator, might be able to open these files, but compatibility is not guaranteed.

The development process follows a few conventions. In order to keep things organized and logical, it is advised that these conventions are to be followed thoroughly. If it makes sense to change these conventions, make sure the documentation (this guide!) is updated.

## Conventions
### Filename
Files are named with the following convention

- All lower case, with multiple words separated by a dash (-).
- Each building has a master file, conveniently named `building-master.svg`.
- Each floor in the building have the convention building-floor. For example, `stanton-1st.svg` or `young-basement.svg`.
- The floors are saved to disk in the directory `dist`.

### Layers
Because each building has multiple floors, each floor lives on its own layer. Typically, these layers include: Basement, 1st Floor, 2nd Floor, 3rd Floor.

Everett is a special case, where each floor is split into 2 layers, short and long. 

### Distribution
After developing for each building, either after creating a new master file or changing it, the following steps are taken to create a distributed copy of each floor.

- The master copy has all of its layers turned off (invisible). This is a convention to distinguish itself from `dist` versions.
- Each floor is its own svg file, which will contain all the floor layers. However, only the layer that contains the named floor will be turned on (visible).
- These floor svg files are then saved in the `dist` directory. This is an example of the tree structure of a folder.

    ```
    stanton
    ├── dist
    │   ├── stanton-1st.svg
    │   ├── stanton-2nd.svg
    │   ├── stanton-3rd.svg
    │   ├── stanton-4th.svg
    │   └── stanton-basement.svg
    ├── index.json
    └── stanton-master.svg
    ```
    
- The distribution step should be done as the last step of the development process. This means that after the last floor is saved, the file should also quit. This convention is helpful to prevent any last minute edits to be applied to a `dist` file and not the `master` copy.

### Text
Font `Arial` is used to maintain compatibility with Windows.
Font sizes:

- Room number/label: 30
- Adjacent building/ directions: 30 Italic
- Building and floor name: 50
- Disclaimer etc.: 20

### Icons
Icons are saved in the `icons.svg` file. Any new icon should be added to there first. Icons can then be used by copying from `icons.svg` to wherever needed.

### Exports
Bitmap exports are sometimes necessary as a way to distribute these floorplans. These exports can be saved in the `exports` folder.

```
exports
└── pngs
    ├── beard
    │   ├── beard-1st.png
    │   └── ...
    ├── chapin
    │   ├── chapin-1st.png
    │   └── ...
    ├── clark
    │   ├── clark-1st.png
    │   └── ...
    ├── everett
    │   ├── everett-1st.png
    │   └── ...
    ├── ...
    └── young
        ├── young-1st.png
        └── ...

18 directories, 66 files
```

When exporting bitmap, remember that the default SVG has a transparent background. If white background is needed, change that before exporting, and be careful to not save the white background back into SVG file (unless that is desired).
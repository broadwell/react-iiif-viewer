# React IIIF Viewer

A React component library built on [OpenSeadragon](https://openseadragon.github.io/) for displaying high resolution images with deep zooming capabilities on mobile and desktop.

Demo

<pic

### What is IIIF?

The "International Image Interoperability Framework", or [IIIF](https://iiif.io/) for short, is an open set of technical standards that provide uniformity to the way image-based resources are presented and delivered to end users.

IIIF images are delivered via a IIIF compatible image server. This server is responsible for breaking down large images into small tiles. The browser then makes requests for these tiles as the user zooms/pans around the image. As the user zooms in deeper, high resolution tiles are requested in order to maintain quality and performance. Fetched tiles are stitched together in real-time resulting in seamless user experience.

Interested in making one of your own images IIIF compatible? Check out [iiifhosting](https://www.iiifhosting.com/). It allows you to host up to 5 images for free.

### Installation

Install via `npm`:

```
$ npm install react-iiif-viewer --save
```

### Components

#### Viewer
A no frills viewer that displays one image at a time.

```
import { Viewer } from "react-iiif-viewer"

const iiifUrl = "https://media.nga.gov/iiif/public/objects/1/0/6/3/8/2/106382-primary-0-nativeres.ptif/info.json"

<Viewer iiifUrl=iiifUrl />
```


| prop      | required | type   | default | description                                                      |
|-----------|----------|--------|---------|------------------------------------------------------------------|
| `iiifUrl` | yes      | string | N/A     | The IIIF image url to display. Changes to this prop will also update the currently displayed image.                    |
| `width`   | no       | string | 800px   | A css dimension for the width of the viewer (500px, 100%, etc.)  |
| `height`  | no       | string | 500px   | A css dimension for the height of the viewer (500px, 100%, etc.) |


#### MultiViewer
A viewer that displays a collection of IIIF images via an expandable/collapsable thumbnail drawer.

```
import { MultiViewer } from "react-iiif-viewer"

const iiifUrls = [
    "https://media.nga.gov/iiif/public/objects/1/0/6/3/8/2/106382-primary-0-nativeres.ptif/info.json",
    "https://media.nga.gov/iiif/public/objects/1/0/6/3/8/2/106382-primary-0-nativeres.ptif/info.json"
]

<MultiViewer iiifUrls={iiifUrls}/>
```

| prop       | required | type     | default | description                                                      |
|------------|----------|----------|---------|------------------------------------------------------------------|
| `iiifUrls` | yes      | [string] | N/A     | An array of IIIF image urls to display                           |
| `width`    | no       | string   | 800px   | A css dimension for the width of the viewer (500px, 100%, etc.)  |
| `height`   | no       | string   | 500px   | A css dimension for the height of the viewer (500px, 100%, etc.) |

### Development

After cloning the repo, install its dependencies:

```
$ cd react-iiif-viewer
$ npm install
```

This project uses [Parcel](https://parceljs.org/) for bundling and running of a development server.

To run the demo application with hot reloading:

```
$ npm run start-demo
```

The unit tests are written using [react-testing-library](https://github.com/testing-library/react-testing-library).

To run them:

```
$ npm test
```
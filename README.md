This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

# Test Instructions

Before you begin, you will need to sign up for a [Google Maps Javascript API key](https://developers.google.com/maps/documentation/javascript/get-api-key). A free one will be fine. If you are unable to do this for some reason, let us know and we can provide one for you.

1. Fork this repo.
2. Make the changes needed to accomplish what is listed below.
3. Deploy this somewhere and send us a link to the deployed app and the repo, then we can schedule some time to meet!

Using your best (simple) design judgment, create an app that does the following:

First, you may choose a data set to use: the ABQ Film Office's list of film locations, **or** the ABQ Public Art location list. The instructions for each are below.

## ABQ Film Data Instructions

- Fetch data from the [ABQ Film Office public dataset](https://coagisweb.cabq.gov/arcgis/rest/services/public/FilmLocations/MapServer/0/query?where=1%3D1&text=&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&relationParam=&outFields=*&returnGeometry=true&maxAllowableOffset=&geometryPrecision=&outSR=4326&returnIdsOnly=false&returnCountOnly=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&returnZ=false&returnM=false&gdbVersion=&f=pjson). This data is a collection of locations where Films/TV/etc have been shot. Documentation found [here](http://data.cabq.gov/business/filmlocations/MetaData.pdf).
    - We only want to see locations with a type of "movie".
    - Keep in mind, there are multiple locations for each movie.
- Create a `select` where we can pick a movie.
- With a movie selected, populate the map with `Marker`s (using [@react-google-maps/api](https://react-google-maps-api-docs.netlify.com/), which is already in the package.json) with the location addresses. These can be derived from the `geometry` key sent back as part of the data. 
- In addition to the `Marker`s, we also expect you to be able to click on the marker and see the shoot date (in human readable format), the shooting site's name, and the site's address. This can be accomplished using the `InfoWindow` component provided by the `@react-google-maps/api` package.

## ABQ Public Art Data Instructions

- Fetch data from the [ABQ Public Art dataset](https://coagisweb.cabq.gov/arcgis/rest/services/public/PublicArt/MapServer/0/query?where=1%3D1&text=&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&relationParam=&outFields=*&returnGeometry=true&maxAllowableOffset=&geometryPrecision=&outSR=4326&returnIdsOnly=false&returnCountOnly=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&returnZ=false&returnM=false&gdbVersion=&returnDistinctValues=false&f=pjson). This data is a collection of locations where public art has been installed. Documentation found [here](http://data.cabq.gov/community/art/publicart/MetaData.pdf/view).
    - We only want to see locations with a type of "mosaics", "public sculpture", "neon sculpture", and "mural paintings (visual works)".
- Create a `select` where we can pick a type of art.
- With the art medium selected, populate the map with `Marker`s (using [@react-google-maps/api](https://react-google-maps-api-docs.netlify.com/), which is already in the package.json) with the location addresses. These can also be derived from the `geometry` key sent back as part of the data. 
- In addition to the `Marker`s, we also expect you to be able to click on the marker and see the pieces title, the year it was installed, the artist's name, and a small preview of the jpg of the art piece. This can be accomplished using the `InfoWindow` component provided by the `@react-google-maps/api` package.

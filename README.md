# address-TW
Open data set of government-released address nodes

## Coordinate system

The default coordinate system is [TWD97 (EPSG:3826)](https://epsg.io/3826). The axes are `easting` (CSV column: `x` or `x_3826`) and `northing` (CSV column: `y` or `y_3826`).

The coordinates can be converted to latitude and longitude (WGS 84, EPSG:4326). Use the transformation descriptions at the bottom of this page: https://epsg.io/3826

Here is a TypeScript example:

```ts
import proj4 from 'proj4';

proj4.defs('EPSG:3826', '+proj=tmerc +lat_0=0 +lon_0=121 +k=0.9999 +x_0=250000 +y_0=0 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs +type=crs');

/**
 * Convert from EPSG:3826 (TWD97) to EPSG:4326 (WGS 84)
 */
function convertTWD97toWGS84(x: number, y: number) {
    const [longitude, latitude] = proj4('EPSG:3826', proj4.WGS84, [x, y]);
    return { latitude, longitude };
}
```


# Tile Server API Documentation

Welcome to the Tile Server API for `gzwmap.com`. This API serves map tiles based on coordinates and provides access to tile data stored. Please read through the documentation before using the API.

## Base URL

```plaintext
https://gzwmap.com
```

## Endpoints

### 1. Home

**Description**: Provides a basic response for the API root.

**Endpoint**: `/`

**Method**: `GET`

**Response**:
- `200 OK` with the message: `Tile server for gzwmap.com`

### 2. Tile Retrieval

**Description**: Retrieves a map tile image based on the specified zoom (`z`), x-coordinate (`x`), and y-coordinate (`y`).

**Endpoint**: `/:z/:x/:y`

**Method**: `GET`

**Parameters**:
- `:z` - The zoom level of the map (integer).
- `:x` - The x-coordinate of the tile (integer).
- `:y` - The y-coordinate of the tile (integer).

**Response**:
- `200 OK` - Returns the requested tile as an image.
- `400 Bad Request` - Invalid tile coordinates or coordinates are out of range.
- `404 Not Found` - Tile not found.
- `500 Internal Server Error` - Internal server error.

**Example**:
```plaintext
GET /5/10/17
```
Returns the tile located at zoom level 5, x-coordinate 10, and y-coordinate 17.

## Map of Tile Ranges

The following is a map of how the tile ranges expand with increasing zoom levels:

| Zoom | Min tile |  -  | Max tile |
|:----:|---------:|:---:|:---------|
|  1   |        0 |  x  | 1        |
|  2   |        0 |  x  | 3        |
|  3   |        0 |  x  | 7        |
|  4   |        0 |  x  | 15       |
|  5   |        0 |  x  | 31       |
|  6   |        0 |  x  | 63       |
|  7   |        0 |  x  | 127      |

## Usage Guidelines

1. **Caching**: Tiles are cached for up to 1 year (`Cache-Control: public, max-age=31536000`).
2. **Valid Coordinates**: Ensure that `z`, `x`, and `y` parameters are valid integers. Invalid values will return a `400 Bad Request`.
3. **Error Handling**: If you encounter an error, a descriptive error message will be returned. Contact support for persistent issues.

## Abuse Policy

- **Rate Limits**: The API is subject to rate limiting. Excessive requests may lead to temporary or permanent bans.
- **Legal Usage**: Accessing tiles for illegal purposes or unauthorized scraping is strictly prohibited.
- **Respectful Access**: Do not overload the server with excessive requests. Please adhere to fair usage practices.

## Contact Information

For support, questions, or to report issues, please contact:
**Email**: [info@gzwmap.com](mailto:info@gzwmap.com)

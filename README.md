# business.json

A file which combines all business-related records from diverse sources.

## Fields

* `Name_of_business` (required) - canonical name of businesses
* `Address` (required) - canonical address of business
* `Coordinates` (required) - An array containing 
	* 'latLon' (required) - An array containing:
		* `latitude` (required) - WGS84 latitude
		* `longitude` (required) - WGS84 longitude
	* Additional arrays may be included to support other coordinate projection systems (e.g., `"xycoordinates": {"y": 0.0, "x": 0.0}`)
* `metadata` (required) - Contains relevant metadata that is helpful to describe subsequent data and timestamps.
	* `sourceName` (required) - describes the corresponding source data set that is included in the file. Name should match corresponding data names below.
	* `sourceUrl` - source of the original data (e.g., a data portal, Plenario, etc.).
	* `idProperty` - field which contains the unique ID for every row.
	* `dateType` - describes whether important dates are a `Range` or an `Exact` date. Depending on 
		* `startDate` and `endDate` (when `"dateType": "Range"`) - expresses the fields for the corresponding start and end dates.
		* `actionDate` (when `"dateType": "Exact"`) - expresses the field that corresponds to the action date.
* Subsequent data fields should correspond to metadata.

## Example

See [an example JSON file](ResultSet.json) and [resulting table view of that file](https://konklone.io/json/?id=a4ae02b59ae7e81225f0bf7a0fb523ca).

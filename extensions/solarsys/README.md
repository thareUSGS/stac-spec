# Solar System Extension Specification

- **Title: Solar System (for planetary data holdings)**
- **Identifier: ssys**
- **Field Name Prefix: ssys**
- **Scope: Item**
- **Extension [Maturity Classification](../README.md#extension-maturity): Pilot**

This document explains the fields of the STAC Solar System (SSYS) Extension to a STAC Item. SSYS
data is considered to be data that represents a snapshot of a planetary body single date and time. It
could consist of multiple spectral bands in any part of the electromagnetic spectrum. Examples of SSYS
data include sensors with visible, short-wave and mid-wave IR bands (e.g., the THEMIS instrument on
Mars Odyssey), visable images (e.g. Context Camera (CTX) aboard Mars Global Surveyor).


A lot of SSYS data will have common metadata across many Items. 
It is not necessary, but recommended to use the [Commons extension](../commons/README.md)
(see chapter "Placing common fields in Collections").

For defining view geometry of data, it is strongly recommended to use the [`view` extension](../view/README.md).

- [Example (THEMIS IR)](examples/mars_THEMIS_IR-sample.json)
- [JSON Schema](json-schema/schema.json)

## Item fields

| Field Name       | Type                     | Description |
| ---------------- | ------------------------ | ----------- |
| ssys:productid   | string                   | **REQUIRED.** Unique string identifier for PDS products. |
| ssys:source      | string URL | **REQUIRED.** A path to the image file used for product creation. |
| ssys:targetname  | string                   | The name of the target. If not available the field should not be provided. |

## Extensions

The [extensions page](../README.md) gives an overview about related extensions. Of particular relevance to SSYS data:

* the [EO Extension Specification](../eo/README.md) to describe observational data collected from a satellite.
* the [View Geometry Extension Specification](../view/README.md) to describe angles of sensors collecting earth observation data from above the earth.

### Placing common fields in Collections
A lot of EO data will have common metadata across many Items. It is not necessary, but recommended	
to use the [Commons extension](../commons/README.md) in combination with [STAC Collections](../../collection-spec/README.md).
The exact metadata that would appear in a STAC Collection record will vary depending on the dataset.

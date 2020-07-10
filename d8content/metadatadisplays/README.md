# What is in this folder?
## Updated Metadata Display Entities/ Twig templates for [Archipelago 8.x-1.0-beta2](https://github.com/esmero/archipelago-deployment/tree/8.x-1.0-beta2)

There are
- two IIIF Manifest generating Twig templates files (.txt) 
- also a GeoJSON template Twig template file (.txt) in this folder.

If you are installing Archipelago Beta2 for the first time you already have these, but if you are updating from Alpha or Beta1 you probably want to:
 - replace http://localhost:8001/metadatadisplay/3 `(IIIF Presentation API 3.0 Manifest)` with 
 the content of `iiif_manifest_3.0-draft.twig.txt` file.
 - add an additional one at `http://localhost:8001/metadatadisplay/list` named `IIIF Presentation API 2.1 Manifest` and set the format to JSONLD using the `iiif_manifest_2.1.twig.txt` file content as source for it.
 - add an additional one at `http://localhost:8001/metadatadisplay/list` named `GeoJSON` and set the format to JSON
using the `geojson.twig.txt` file content as source for it.

## Where are these templates used? 

Several Field Formatters (viewers) use as input IIIF Manifests generated by these. 
Archipelago exposes also Metadata endpoints which can be configured to use any of template at 
`http://localhost:8001/admin/config/archipelago/metadataexpose`, per Content Type. 
In specific, the GeoJSON one provides support for the new [Map Formatter](https://github.com/esmero/format_strawberryfield/blob/8.x-1.0-beta2/src/Plugin/Field/FieldFormatter/StrawberryMapFormatter.php ).

## Need help?

Please post to https://groups.google.com/forum/#!forum/archipelago-commons or open an issue
at https://github.com/esmero/archipelago-deployment and we will be happy to help you with this
or any other issue!
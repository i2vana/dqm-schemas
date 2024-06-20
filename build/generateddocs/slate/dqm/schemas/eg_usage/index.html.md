---
title: Example Feature with DQM (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>Example Feature with DQM</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Example Feature with DQM (Schema)
---


# Example Feature with DQM `ogc.dqm.schemas.eg_usage`

Example of defining a feature with a specific DQM property

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/dqm-schemas/blob/master/build/tests/dqm/schemas/eg_usage/" target="_blank">valid</a></strong>
</aside>

# Description

## Feature with a DQM property

NB Records and STAC items are features and can be profiled with this model.


# Examples

## STAC item with link to provenance



```json
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862874
      ]
    ]
  },
  "properties": {
    "extraneous_nodes": 3
  }
}

```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/eg_usage/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Feg_usage%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862875
      ]
    ]
  },
  "properties": {
    "extraneous_nodes": 3
  },
  "@context": "https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/eg_usage/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Feg_usage%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://example.com/dqm/example1/f1> a geojson:Feature ;
    dqm:21 3 ;
    geojson:geometry [ a geojson:LineString ;
            geojson:coordinates ( ( -1.116718e+02 4.005671e+01 ) ( -1.1171e+02 4.015671e+01 ) ) ] .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/eg_usage/example_1_1.ttl">Open in new window</a>
</blockquote>


Example GeoJSON feature with a DQM property



# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: Example of a sinmple GeoJSON Feature specialisation with a DQM measure
$defs:
  MyFeature:
    allOf:
    - $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
    - properties:
        properties:
          allOf:
          - $ref: https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/schema.yaml
          - required:
            - extraneous_nodes
$ref: '#/$defs/MyFeature'

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Feg_usage%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/schema.yaml" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/schema.json" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:geometry"
    },
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "extraneous_nodes": "dqm:21",
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "dqm": "http://www.opengis.net/def/metamodel/isodqm/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Feg_usage%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/context.jsonld" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/eg_usage/context.jsonld</a>

# References

* [GeoDCAT Specification](http://www.opengis.net/def/metamodel/profiles/geodcat)
* [PROV-O Specification](https://www.w3.org/TR/prov-o/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/dqm-schemas" target="_blank">https://github.com/ogcincubator/dqm-schemas</a>
* Path:
<code><a href="https://github.com/ogcincubator/dqm-schemas/blob/HEAD/_sources/eg_usage" target="_blank">_sources/eg_usage</a></code>


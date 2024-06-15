---
title: Measure (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>Measure</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Measure (Schema)
---


# Measure `ogc.dqm.schemas.measure`

Utility datatype for a Measure, a numerical value with a units of measure. The QUDT namespaces is defined by default, but may be overridden by a well formed URI or CURIE pattern.

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/dqm-schemas/blob/master/build/tests/dqm/schemas/measure/" target="_blank">valid</a></strong>
</aside>

# Description

## My Schema

Defines a set of properties that may be used in **any** JSON schema.

> Note these properties may be used in the "properties" sub-component of a GeoJSON object, as a simple object

The numeric properties "b" and "c" have an example SHACL rule that if c is present, then c > b
# Examples

## Default units



```json
{ "value": 3,
  "units": "M"
}
```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fmeasure%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "value": 3,
  "units": "M",
  "@context": "https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fmeasure%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dqm:measureValue 3 ;
    dqm:units <https://qudt.org/vocab/unit/M> .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_1_1.ttl">Open in new window</a>
</blockquote>


example using default namespace for UOM


## Custom units



```json
{ "value": 27.2,
  "units": "http://mydomain.org/units/foogles-per-thrunge"
}
```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_2_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fmeasure%2Fexample_2_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "value": 27.2,
  "units": "http://mydomain.org/units/foogles-per-thrunge",
  "@context": "https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_2_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fmeasure%2Fexample_2_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dqm:measureValue 2.72e+01 ;
    dqm:units <http://mydomain.org/units/foogles-per-thrunge> .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/tests/dqm/schemas/measure/example_2_1.ttl">Open in new window</a>
</blockquote>


example using a custom namespace for UOM


# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: DQM extraneous nodes
$defs:
  Measure:
    properties:
      value:
        type: number
        x-jsonld-id: http://www.opengis.net/def/metamodel/isodqm/measureValue
      units:
        $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/ogc-utils/iri-or-curie/schema.yaml
        x-jsonld-type: '@id'
        x-jsonld-id: http://www.opengis.net/def/metamodel/isodqm/units
        x-jsonld-base: https://qudt.org/vocab/unit/
oneOf:
- $ref: '#/$defs/Measure'
x-jsonld-prefixes:
  dqm: http://www.opengis.net/def/metamodel/isodqm/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Fmeasure%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/schema.yaml" target="_blank">https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/schema.yaml</a>
* JSON version: <a href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/schema.json" target="_blank">https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "value": "dqm:measureValue",
    "units": {
      "@context": {
        "@base": "https://qudt.org/vocab/unit/"
      },
      "@type": "@id",
      "@id": "dqm:units"
    },
    "dqm": "http://www.opengis.net/def/metamodel/isodqm/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fdqm-schemas%2Fmaster%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Fmeasure%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/context.jsonld" target="_blank">https://raw.githubusercontent.com/ogcincubator/dqm-schemas/master/build/annotated/dqm/schemas/measure/context.jsonld</a>

# References

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/dqm-schemas" target="_blank">https://github.com/ogcincubator/dqm-schemas</a>
* Path:
<code><a href="https://github.com/ogcincubator/dqm-schemas/blob/HEAD/_sources/measure" target="_blank">_sources/measure</a></code>


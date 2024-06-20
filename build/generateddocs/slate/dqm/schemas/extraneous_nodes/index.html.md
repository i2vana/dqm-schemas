---
title: DQM 21 extraneous nodes (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>DQM 21 extraneous nodes</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: DQM 21 extraneous nodes (Schema)
---


# DQM 21 extraneous nodes `ogc.dqm.schemas.extraneous_nodes`

number of faulty point-curve connections in the dataset

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/dqm-schemas/blob/master/build/tests/dqm/schemas/extraneous_nodes/" target="_blank">valid</a></strong>
</aside>

# Description

## My Schema

Defines a set of properties that may be used in **any** JSON schema.

> Note these properties may be used in the "properties" sub-component of a GeoJSON object, as a simple object

The numeric properties "b" and "c" have an example SHACL rule that if c is present, then c > b
# Examples

## Examples



```json
{
      "extraneous_nodes": 2
}
```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/extraneous_nodes/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fextraneous_nodes%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "extraneous_nodes": 2,
  "@context": "https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/extraneous_nodes/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Ftests%2Fdqm%2Fschemas%2Fextraneous_nodes%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dqm:21 2 .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/dqm-schemas/build/tests/dqm/schemas/extraneous_nodes/example_1_1.ttl">Open in new window</a>
</blockquote>


The content of this example. 


# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: DQM extraneous nodes
$defs:
  extraneous_nodes_value:
    type: number
properties:
  extraneous_nodes:
    $ref: '#/$defs/extraneous_nodes_value'
    x-jsonld-id: http://www.opengis.net/def/metamodel/isodqm/21
x-jsonld-prefixes:
  dqm: http://www.opengis.net/def/metamodel/isodqm/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Fextraneous_nodes%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/schema.yaml" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/schema.json" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "extraneous_nodes": "dqm:21",
    "dqm": "http://www.opengis.net/def/metamodel/isodqm/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fdqm-schemas%2Fbuild%2Fannotated%2Fdqm%2Fschemas%2Fextraneous_nodes%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/context.jsonld" target="_blank">https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/extraneous_nodes/context.jsonld</a>

# References

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/dqm-schemas" target="_blank">https://github.com/ogcincubator/dqm-schemas</a>
* Path:
<code><a href="https://github.com/ogcincubator/dqm-schemas/blob/HEAD/_sources/extraneous_nodes" target="_blank">_sources/extraneous_nodes</a></code>


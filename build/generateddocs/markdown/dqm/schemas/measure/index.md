
# Measure (Schema)

`ogc.dqm.schemas.measure` *v0.1*

Utility datatype for a Measure, a numerical value with a units of measure. The QUDT namespaces is defined by default, but may be overridden by a well formed URI or CURIE pattern.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## My Schema

Defines a set of properties that may be used in **any** JSON schema.

> Note these properties may be used in the "properties" sub-component of a GeoJSON object, as a simple object

The numeric properties "b" and "c" have an example SHACL rule that if c is present, then c > b
## Examples

### Default units
example using default namespace for UOM
#### json
```json
{ "value": 3,
  "units": "M"
}
```

#### jsonld
```jsonld
{
  "value": 3,
  "units": "M",
  "@context": "https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/measure/context.jsonld"
}
```

#### ttl
```ttl
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dqm:measureValue 3 ;
    dqm:units <https://qudt.org/vocab/unit/M> .


```


### Custom units
example using a custom namespace for UOM
#### json
```json
{ "value": 27.2,
  "units": "http://mydomain.org/units/foogles-per-thrunge"
}
```

#### jsonld
```jsonld
{
  "value": 27.2,
  "units": "http://mydomain.org/units/foogles-per-thrunge",
  "@context": "https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/measure/context.jsonld"
}
```

#### ttl
```ttl
@prefix dqm: <http://www.opengis.net/def/metamodel/isodqm/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dqm:measureValue 2.72e+01 ;
    dqm:units <http://mydomain.org/units/foogles-per-thrunge> .


```

## Schema

```yaml
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

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/measure/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/measure/schema.yaml)


# JSON-LD Context

```jsonld
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

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/dqm-schemas/build/annotated/dqm/schemas/measure/context.jsonld)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/dqm-schemas](https://github.com/ogcincubator/dqm-schemas)
* Path: `_sources/measure`


# Changelog

All notable changes to this repository will be documented in this file.

This repository follows a simple versioning approach for the Insurance Ontology and its related artefacts.

## Versioning approach

Version numbers follow this pattern:

`MAJOR.MINOR`

Examples:

1. `1.0`
2. `1.1`
3. `2.0`

### Interpretation

1. **MAJOR** version changes represent significant structural or semantic change
2. **MINOR** version changes represent additive or refinement based updates that do not fundamentally change the ontology direction

## Change types

Changes may include:

1. new entity
2. updated definition
3. new relationship
4. new attribute
5. vocabulary extension
6. new example
7. new schema
8. new mapping template
9. documentation improvement
10. deprecation or refactor

## [1.0] , 14 April 2026

### Added

#### Repository structure
1. Initial repository structure created
2. Root `README.md` added
3. `docs` folder added
4. `core` folder added
5. `vocabularies` folder added
6. `modules` folder added
7. `examples` folder added
8. `mappings` folder added

#### Documentation
1. Added `docs/ontology_principles.md`
2. Added `docs/modelling_conventions.md`

#### Core ontology
1. Added `core/core_entity_catalogue.yaml`
2. Added `vocabularies/shared_vocabularies.yaml`

#### Product modules
1. Added `modules/motor/motor_entities.yaml`
2. Added `modules/motor/motor_vocabularies.yaml`
3. Added `modules/home/home_entities.yaml`
4. Added `modules/home/home_vocabularies.yaml`
5. Added `modules/commercial_property/commercial_property_entities.yaml`
6. Added `modules/commercial_property/commercial_property_vocabularies.yaml`
7. Added `modules/pensions/pensions_entities.yaml`
8. Added `modules/pensions/pensions_vocabularies.yaml`

#### Examples
1. Added `examples/motor_policy_example.json`
2. Added `examples/home_policy_example.json`
3. Added `examples/commercial_property_policy_example.json`
4. Added `examples/pension_member_example.json`

#### Schemas
1. Added `modules/motor/motor_policy_schema.json`
2. Added `modules/home/home_policy_schema.json`
3. Added `modules/commercial_property/commercial_property_policy_schema.json`
4. Added `modules/pensions/pension_member_schema.json`

#### Mapping templates
1. Added `mappings/source_to_canonical_template.yaml`
2. Added `mappings/wording_term_mapping_template.yaml`

### Notes

1. Version `1.0` establishes the initial ontology foundation
2. Scope includes UK aligned Motor, Home, Commercial Property, and UK specific Pensions
3. This version focuses on practical ontology structure, examples, mappings, and schema foundations
4. Future versions may expand into additional insurance lines, deeper claims modelling, and stronger schema validation

# Modelling Conventions

## Purpose

This document defines the conventions used across the Insurance Ontology repository so that entities, attributes, relationships, vocabularies, examples, and mappings are structured consistently.

These conventions are intended to improve:

1. readability
2. consistency
3. reusability
4. maintainability
5. implementation readiness

## General principles

### 1. Prefer business language

Use names that reflect real business meaning rather than system specific terminology.

Good examples:

1. Policy
2. Coverage
3. Policyholder
4. Commercial Premises
5. Pension Member

Avoid using:

1. platform specific field names
2. internal abbreviations unless clearly established
3. technical table style labels as ontology entity names

### 2. Keep concepts singular

Entity names should be singular.

Good examples:

1. Policy
2. Vehicle
3. Claim
4. Pension Scheme

Not preferred:

1. Policies
2. Vehicles
3. Claims

### 3. Shared first, specialised second

If a concept applies across multiple modules, define it in the shared core first.

Only define product specific entities in module folders where there is a genuine business need.

Example:

1. Policy belongs in shared core
2. Vehicle belongs in the Motor module
3. Property belongs in the Home module
4. Pension Account belongs in the Pensions module

### 4. Meaning before implementation

The ontology defines business meaning first.

It does not need to mirror:

1. one source system
2. one database table
3. one API payload
4. one document layout

Implementation artefacts may vary, but the ontology should remain semantically stable.

## Naming conventions

### Entity names

In documentation, use title case for entity names.

Examples:

1. Policy
2. Policyholder
3. Home Coverage
4. Pension Benefit

In YAML structures where the entity appears as a key, use lowercase snake_case.

Examples:

1. policy
2. policyholder
3. home_coverage
4. pension_benefit

### Attribute names

Use lowercase snake_case for all attributes.

Examples:

1. policy_number
2. inception_date
3. payment_frequency
4. current_fund_value

Do not use:

1. camelCase
2. PascalCase
3. space separated names
4. inconsistent abbreviations

### File names

Use lowercase snake_case for file names.

Examples:

1. ontology_principles.md
2. core_entity_catalogue.yaml
3. shared_vocabularies.yaml
4. motor_entities.yaml
5. home_policy_example.json

### Folder names

Use lowercase for folder names.

Examples:

1. docs
2. core
3. vocabularies
4. modules
5. examples
6. mappings

## Definition conventions

### How to write definitions

Definitions should be:

1. clear
2. concise
3. business meaningful
4. non circular
5. distinct from nearby concepts

A good definition should explain what the concept is, not just repeat its name.

Good example:

**Policy**  
A contractual agreement under which coverage is provided in exchange for premium, subject to terms, conditions, exclusions, and limits.

Weak example:

**Policy**  
A policy record for insurance policies.

### Definition style rules

1. Start with the business concept itself
2. Explain the concept in plain language
3. Avoid implementation wording unless needed
4. Avoid vague phrases such as "used for many purposes"
5. Distinguish from similar concepts where necessary

## Relationship conventions

Relationships should be written in simple, business readable form.

Preferred verbs:

1. has
2. contains
3. applies to
4. modifies
5. relates to
6. arises from
7. is evidenced by
8. belongs to
9. participates in
10. sponsors

Examples:

1. Policy has Policyholder
2. Policy contains Coverage
3. Coverage applies to Insured Object
4. Endorsement modifies Policy
5. Claim arises from Loss Event
6. Pension Account belongs to Pension Member

Relationship statements should be easy for business and technical teams to read without translation.

## Attribute conventions

### Attribute selection

Only include attributes that materially help define or use the concept.

Avoid adding too many attributes too early.

Version 1 should focus on attributes that are:

1. commonly used
2. useful for mapping
3. useful for document extraction
4. useful for examples and schemas

### Attribute scope

Attributes should belong to the concept they most naturally describe.

Example:

1. `policy_number` belongs to Policy
2. `registration_number` belongs to Vehicle
3. `contribution_amount` belongs to Contribution
4. `construction_type` belongs to Property or Commercial Premises depending on context

Do not attach attributes to the wrong concept simply because one source system stores them there.

## Vocabulary conventions

Controlled vocabularies should be managed separately from entity definitions where possible.

Each vocabulary should include:

1. vocabulary name
2. description
3. allowed values

Vocabulary values should use lowercase snake_case.

Examples:

1. active
2. cancelled
3. owner_occupied
4. defined_contribution

Where a code list is product specific, place it in the relevant module vocabulary file.

Where a code list is reused, place it in `shared_vocabularies.yaml`.

## Module conventions

Each module should align to the shared foundation.

A module file should:

1. define only concepts relevant to that module
2. extend shared entities where appropriate
3. avoid redefining shared concepts unnecessarily
4. keep terminology consistent with the core catalogue

Examples:

1. `motor_policy` extends `Policy`
2. `home_coverage` extends `Coverage`
3. `commercial_property_coverage` extends `Coverage`
4. `pension_account` extends `Pension Account`

## Example payload conventions

Example JSON files should show how the ontology can be used in practice.

Examples should be:

1. realistic
2. internally consistent
3. aligned to module vocabularies
4. easy to read

Examples should not try to represent every possible field or edge case.

They are illustrations, not full production payloads.

### JSON naming

JSON keys should use lowercase snake_case.

### Dates

Use ISO format where possible.

Example:

`2026-01-01`

### Currency

Use standard currency codes such as:

1. GBP
2. EUR
3. USD

## Mapping conventions

### Source to canonical mappings

Mappings should always identify:

1. source system
2. source field
3. canonical entity
4. canonical field path
5. transformation rule
6. validation rule

This allows the ontology to support real data integration and extraction use cases.

### Wording term mappings

Wording term mappings should capture:

1. source term
2. source term variant
3. canonical field path
4. extraction context
5. ambiguity notes
6. confidence guidance

This is especially important where the same wording may mean different things in different contexts.

## UK conventions

Where a concept is explicitly UK specific, that should be stated clearly in the relevant module or file.

This applies especially to Pensions.

Examples of UK specific concepts include:

1. auto_enrolment
2. relief_at_source
3. net_pay_arrangement
4. salary_sacrifice

Do not assume all modules are UK specific unless stated.
For this repository, Motor, Home, and Commercial Property are currently modelled in a UK aligned context, while Pensions is explicitly UK specific.

## Extension conventions

When extending the ontology in future versions:

1. prefer adding new concepts over changing core meanings
2. avoid breaking existing canonical names without strong reason
3. document any major semantic changes clearly
4. place new product specific concepts in the relevant module
5. update examples and mappings where relevant

## Versioning conventions

Changes should be treated as one of the following:

1. new entity
2. updated definition
3. new relationship
4. new attribute
5. new vocabulary value
6. new example
7. deprecation
8. structural refactor

Version increments should reflect meaningful changes to repository content.

## Quality checks

Before adding or updating a concept, check:

1. Is the name business meaningful?
2. Is the definition clear?
3. Is the concept already defined elsewhere?
4. Are the relationships explicit?
5. Are the attributes relevant?
6. Should this be in shared core or a module?
7. Does it need a controlled vocabulary?
8. Does it need an example or mapping update?

## Summary

These conventions exist to ensure that the ontology remains:

1. coherent
2. modular
3. readable
4. extensible
5. practically useful

All future additions should follow these conventions unless there is a clear reason to do otherwise.

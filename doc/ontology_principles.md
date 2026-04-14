# Ontology Principles

## Purpose

The purpose of this ontology is to provide a shared business meaning for insurance and pensions concepts so that data, documents, systems, and product structures can be interpreted consistently across use cases.

This ontology is intended to support:

1. business understanding
2. domain modelling
3. canonical data design
4. document analysis
5. source to target mapping
6. integration design
7. analytics and AI use cases

## Core principles

### 1. Business meaning comes first

The ontology must reflect real business concepts used in insurance and pensions.

Concepts should be defined according to business meaning rather than system specific labels or table structures.

For example, a Policy is a business concept first. It should not be defined only by how one administration system stores it.

### 2. One concept, one meaning

Each concept should have one primary meaning across the ontology.

Synonyms and alternative labels may exist, but they should map back to one canonical concept.

For example:

1. Policyholder
2. Customer
3. Contract holder

These may appear in different contexts, but the ontology must make clear whether they refer to the same concept or to different concepts.

### 3. Shared foundation before product variation

Common concepts should be defined once in the shared foundation before product specific specialisation is introduced.

For example:

1. Party
2. Policy
3. Coverage
4. Premium
5. Risk
6. Document

These should exist at the shared level, while concepts such as Vehicle or Property should sit in product or asset specific modules.

### 4. Modular structure

The ontology should be organised into modules so that it remains manageable and extensible.

The main modules for Version 1 are:

1. shared core
2. motor insurance
3. home insurance
4. commercial property insurance
5. pensions

Each module should align to the shared foundation and avoid redefining concepts unnecessarily.

### 5. Canonical and reusable

The ontology should act as a canonical reference point for mapping data from different systems and documents.

Where multiple labels exist for the same concept, the ontology should preserve the source variation but map it to one canonical form.

For example:

1. Sum Insured
2. Declared Value
3. Cover Amount

These may need to map to distinct canonical concepts or one shared concept depending on business meaning. The ontology should make that distinction explicit.

### 6. Clear boundaries between concepts

The ontology should distinguish related but different concepts.

For example:

1. Policy is not the same as Policy Document
2. Endorsement is not the same as Endorsement Document
3. Policyholder is not always the same as Insured
4. Coverage is not the same as Premium
5. Risk is not the same as Claim

This is important because insurance terminology is often used loosely in practice.

### 7. Product agnostic where possible

Shared concepts should be defined in a product neutral way wherever possible.

For example, Coverage should be defined broadly enough to apply across Motor, Home, Commercial Property, and relevant pension benefit structures where appropriate.

Only introduce product specific concepts when there is a genuine structural difference.

### 8. Extensible by design

The ontology should support future extension into other domains without breaking existing concepts.

Possible future extensions may include:

1. liability insurance
2. travel insurance
3. marine insurance
4. life and protection
5. reinsurance
6. claims deepening
7. underwriting decision support

This means entity naming, hierarchy, and vocabulary design should allow growth.

### 9. Document aware

Insurance meaning often comes from documents as much as from systems.

The ontology should support concepts and labels found in:

1. policy wordings
2. schedules
3. endorsements
4. proposal forms
5. certificates
6. claims forms
7. pension scheme documents

The ontology should therefore allow alternative labels, wording variants, and contextual notes.

### 10. Human readable and machine usable

Each concept should be easy for business and architecture teams to understand, while also being structured enough for implementation.

Every entity should aim to include:

1. entity name
2. business definition
3. parent domain
4. core relationships
5. core attributes
6. synonyms where relevant
7. applicable products or business areas

### 11. Separate meaning from implementation

The ontology defines meaning. It does not define a database design by default.

A concept in the ontology may later be implemented in one table, many tables, one API object, or several services.

For example, Coverage may exist as:

1. a business concept in the ontology
2. an entity in the domain model
3. several structures in the logical data model
4. multiple fields across source systems

The ontology should remain stable even when implementation varies.

### 12. Explicit relationships matter

The ontology should describe not only what concepts exist, but how they relate to each other.

Examples include:

1. Policy has Policyholder
2. Policy contains Coverage
3. Coverage applies to Insured Object
4. Claim arises from Loss Event
5. Endorsement modifies Policy
6. Property is located at Address
7. Employer sponsors Pension Scheme

These relationships form the semantic backbone of the ontology.

### 13. Controlled vocabularies should be governed

Where a concept relies on a set of allowed values, those values should be defined and governed separately.

Examples include:

1. policy status
2. coverage type
3. property type
4. construction type
5. vehicle use type
6. contribution frequency

Controlled vocabularies should be versioned and referenced consistently.

### 14. Avoid over modelling early

The ontology should begin with the minimum level of detail needed to be useful.

Version 1 should focus on conceptual clarity and practical implementation value, rather than trying to represent every edge case from the start.

It is better to have a coherent first version than a highly detailed but unstable model.

### 15. Versioning should be incremental

The ontology should evolve in controlled increments.

Changes should be categorised as:

1. new concept
2. updated definition
3. new relationship
4. vocabulary extension
5. deprecation of concept
6. structural refactor

Versioning should make it clear what has changed and why.

## Modelling conventions

### Entity naming

1. Use singular nouns for entity names
2. Use business meaningful names
3. Avoid system specific abbreviations where possible
4. Use title case for entity names in documentation
5. Use snake_case for machine readable attribute names

Examples:

1. Policy
2. Coverage
3. Pension Member
4. Commercial Premises

Examples of attribute names:

1. policy_number
2. inception_date
3. excess_amount
4. contribution_frequency

### Definitions

Definitions should:

1. be clear and concise
2. describe the business meaning
3. avoid circular wording
4. avoid system specific references unless needed
5. distinguish the concept from nearby concepts

### Relationships

Relationships should be expressed using active and understandable verbs.

Examples:

1. has
2. contains
3. applies to
4. modifies
5. arises from
6. is evidenced by
7. is located at

### Synonyms

Synonyms may be listed where a concept appears under multiple business terms.

Synonyms should not replace the canonical name.

### Product applicability

Each concept should note whether it applies to:

1. all modules
2. a subset of modules
3. one product line only

This helps distinguish shared concepts from specialised ones.

## Relationship to other modelling artefacts

The ontology sits alongside, but is different from, other modelling artefacts.

### Ontology
Defines meaning and relationships.

### Domain model
Defines scoped business structures for a domain such as Policy or Claims.

### Logical data model
Defines implementation ready entities and relationships for data design.

### Physical model
Defines storage structures in a platform or database.

In simple terms:

1. ontology explains what things mean
2. domain model organises those things for a business domain
3. logical model prepares those things for implementation

## Version 1 priorities

Version 1 should prioritise:

1. shared core entity catalogue
2. shared business definitions
3. shared relationships
4. controlled vocabularies
5. Motor module
6. Home module
7. Commercial Property module
8. Pensions module
9. sample schemas
10. mapping templates

## Success criteria

The ontology will be considered useful if it:

1. provides clear and reusable business concepts
2. reduces ambiguity across products and systems
3. supports domain modelling and canonical design
4. supports document and source mapping
5. can be extended without major redesign
6. is understandable by business and technical teams

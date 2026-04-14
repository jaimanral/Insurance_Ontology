# Insurance Ontology

## Overview

This repository contains a practical insurance ontology designed to standardise business concepts, relationships, and terminology across selected insurance and pensions domains.

The initial scope includes:

1. Motor Insurance
2. Home Insurance
3. Commercial Property Insurance
4. Pensions

The ontology is intended to support consistent modelling, document analysis, data mapping, integration, and AI enabled use cases.

## Purpose

The purpose of this ontology is to provide a shared semantic foundation for insurance and pensions data so that information coming from different documents, systems, products, and business teams can be understood in a consistent way.

This repository is designed to help with:

1. ontology development
2. domain modelling
3. canonical data modelling
4. policy and product analysis
5. document parsing and extraction
6. source to target data mapping
7. API and integration design
8. analytics and AI use cases

## Why this ontology exists

Insurance data is often fragmented across:

1. policy wordings
2. schedules
3. endorsements
4. proposal forms
5. policy administration systems
6. claims platforms
7. spreadsheets
8. broker submissions
9. pension scheme documents

The same business concept may appear in different places using different labels, structures, or wording. This makes comparison, analysis, integration, and automation difficult.

This ontology provides a common business vocabulary and structure to address that problem.

## Scope

Version 1 focuses on four domains:

1. Motor Insurance
2. Home Insurance
3. Commercial Property Insurance
4. Pensions

The ontology includes:

1. shared core concepts
2. product specific modules
3. controlled vocabularies
4. canonical entity definitions
5. example schemas
6. example data instances
7. mapping templates for documents and source systems

## Design principles

The ontology is built using the following principles:

1. Business first  
   Concepts should reflect real insurance and pensions business meaning.

2. Modular  
   Shared concepts should sit in a common foundation, while product specific concepts should sit in separate modules.

3. Canonical  
   Each concept should have one clear meaning and one standard representation.

4. Extensible  
   The model should support future expansion into additional insurance products and business domains.

5. Practical  
   The ontology should support implementation, not just conceptual modelling.

6. Document aware  
   The ontology should support terms found in policy wordings, schedules, endorsements, and similar documents.

## Repository structure

```text
insurance_ontology/
  README.md

  core/
    party.yaml
    contract.yaml
    risk.yaml
    asset.yaml
    claims.yaml
    document.yaml

  modules/
    motor/
      motor_entities.yaml
      motor_vocabularies.yaml
      motor_policy_schema.json
      motor_quote_schema.json

    home/
      home_entities.yaml
      home_vocabularies.yaml
      home_policy_schema.json
      home_quote_schema.json

    commercial_property/
      commercial_property_entities.yaml
      commercial_property_vocabularies.yaml
      commercial_property_policy_schema.json

    pensions/
      pensions_entities.yaml
      pensions_vocabularies.yaml
      pension_scheme_schema.json
      pension_member_schema.json

  vocabularies/
    shared_vocabularies.yaml

  mappings/
    source_to_canonical_template.yaml
    wording_term_mapping_template.yaml

  examples/
    motor_policy_example.json
    home_policy_example.json
    commercial_property_policy_example.json
    pension_member_example.json

  docs/
    ontology_principles.md
    modelling_conventions.md
    versioning_approach.md

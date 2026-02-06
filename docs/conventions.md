# Ontology conventions (draft summary)

## Labeling

- OWL classes and properties: use `rdfs:label` as the human-friendly preferred name (no IDs/codes).
- SKOS concepts: use `skos:prefLabel` as the preferred name.
- Synonyms / abbreviations:
  - SKOS: `skos:altLabel` (multiple allowed).
  - OWL: `oboInOwl:hasExactSynonym` (when you need an exact synonym).

## Definitions and provenance

- Prefer IAO annotation properties for definitions and documentation:
  - `IAO:0000115` — definition
  - `IAO:0000119` — definition source / rationale
  - `IAO:0000112` — example usage
- Use `dcterms:source` and/or `rdfs:comment` for provenance and notes.

## Modeling guidance

- Do **not** model the same term as both an OWL class and a SKOS concept.
- Use `rdfs:domain` and `rdfs:range` carefully and consistently for properties.
- For “has member” semantics, align with RO where appropriate (e.g., RO:0002351), and avoid inventing near-duplicates.
- If a property is intended to be transitive, define it as an `owl:TransitiveProperty` (don’t use ad-hoc booleans).

## Mapping / alignment

- Use `skos:exactMatch` for cross-ontology mappings.
- Use `rdfs:seeAlso` for supporting links and related terms.

## TODO

This page is a draft summary. Next step is to extract a clean, structured convention doc from the downloaded analysis and align it with the actual ontology repo structure.

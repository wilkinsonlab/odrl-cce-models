## Use by Commercial Entity

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit
Agreement,https://example.com/policy:01,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,odrl:industry,odrl:eq,http://purl.obolibrary.org/obo/ICO_0000049,
Agreement,https://example.com/policy:02,,permission,odrl:read,https://example.come/Apple,https://example.copm/user/2,https://example.copm/asset:02,odrl:purpose,odrl:isA,http://purl.obolibrary.org/obo/DOID_4,
```

|type     |uid                          |profile|rule_type |rule_action|rule_assigner             |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro               |rule_assignee_refinement_unit|
|---------|-----------------------------|-------|----------|-----------|--------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|------------------------------------------|-----------------------------|
|Agreement|https://example.com/policy:01|       |permission|use        |https://example.come/Sony |https://example.copm/user/1|https://example.copm/asset:01|odrl:industry              |odrl:eq                   |http://purl.obolibrary.org/obo/ICO_0000049|                             |
|Agreement|https://example.com/policy:02|       |permission|read       |https://example.come/Apple|https://example.copm/user/2|https://example.copm/asset:02|odrl:purpose               |odrl:isA                  |http://purl.obolibrary.org/obo/DOID_4     |                             |

### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  obo: http://purl.obolibrary.org/obo/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assigner, $(rule_assigner)]
      - p: odrl:assignee
        o:
          mapping: rule_assignee
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - p: odrl:source
        o: odrl:$(rule_assignee)
      - p: odrl:refinement
        o:
          mapping: rule_assignee_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Geographical Area

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit
Agreement,https://example.com/policy:01,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,odrl:spatialCoordinates,odrl:eq,https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/ES,
Agreement,https://example.com/policy:02,,permission,odrl:read,https://example.come/Apple,https://example.copm/user/2,https://example.copm/asset:02,odrl:spatialCoordinates,odrl:neq,https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/RU,
```

|type     |uid                          |profile|rule_type |rule_action|rule_assigner             |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro                                     |rule_assignee_refinement_unit|
|---------|-----------------------------|-------|----------|-----------|--------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|----------------------------------------------------------------|-----------------------------|
|Agreement|https://example.com/policy:01|       |permission|use        |https://example.come/Sony |https://example.copm/user/1|https://example.copm/asset:01|odrl:spatialCoordinates    |odrl:eq                   |https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/ES|                             |
|Agreement|https://example.com/policy:02|       |permission|read       |https://example.come/Apple|https://example.copm/user/2|https://example.copm/asset:02|odrl:spatialCoordinates    |odrl:neq                  |https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/RU|                             |


### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  obo: http://purl.obolibrary.org/obo/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assigner, $(rule_assigner)]
      - p: odrl:assignee
        o:
          mapping: rule_assignee
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - p: odrl:source
        o: odrl:$(rule_assignee)
      - p: odrl:refinement
        o:
          mapping: rule_assignee_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Regulatory Jurisdiction

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit
Agreement,https://example.com/policy:01,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,odrl:spatialCoordinates,odrl:eq,https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/ES,
Agreement,https://example.com/policy:02,,permission,odrl:read,https://example.come/Apple,https://example.copm/user/2,https://example.copm/asset:02,odrl:spatialCoordinates,odrl:neq,https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/RU,
```

|type     |uid                          |profile               |rule_type |rule_action|rule_assigner             |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro                                                                                                          |rule_assignee_refinement_unit|
|---------|-----------------------------|----------------------|----------|-----------|--------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
|Agreement|https://example.com/policy:01|https://w3id.org/occe/|permission|odrl:use   |https://example.come/Sony |https://example.copm/user/1|https://example.copm/asset:01|occe:jurisdiction          |odrl:isA                  |https://spec.edmcouncil.org/fibo/ontology/BE/GovernmentEntities/NorthAmericanJurisdiction/CAGovernmentEntitiesAndJurisdictions/      |                             |
|Agreement|https://example.com/policy:02|https://w3id.org/occe/|permission|odrl:read  |https://example.come/Apple|https://example.copm/user/2|https://example.copm/asset:02|occe:jurisdiction          |odrl:isA                  |https://spec.edmcouncil.org/fibo/ontology/BE/GovernmentEntities/EuropeanJurisdiction/EasternEuropeGovernmentEntitiesAndJurisdictions/|                             |

### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  obo: http://purl.obolibrary.org/obo/
  occe: https://w3id.org/occe/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assigner, $(rule_assigner)]
      - p: odrl:assignee
        o:
          mapping: rule_assignee
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - p: odrl:source
        o: odrl:$(rule_assignee)
      - p: odrl:refinement
        o:
          mapping: rule_assignee_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Research Use

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit,rule_action_refinement_lo,rule_action_refinement_o,rule_action_refinement_ro,rule_action_refinement_unit
Agreement,https://example.com/policy:01,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/dpv#ResearchAndDevelopment,
Agreement,https://example.com/policy:02,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/dpv#ResearchAndDevelopment,
```

|type     |uid                          |profile|rule_type |rule_action|rule_assigner            |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro|rule_assignee_refinement_unit|rule_action_refinement_lo|rule_action_refinement_o|rule_action_refinement_ro                  |rule_action_refinement_unit|
|---------|-----------------------------|-------|----------|-----------|-------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|---------------------------|-----------------------------|-------------------------|------------------------|-------------------------------------------|---------------------------|
|Agreement|https://example.com/policy:01|       |permission|odrl:use   |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/dpv#ResearchAndDevelopment|                           |
|Agreement|https://example.com/policy:02|       |permission|odrl:use   |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/dpv#ResearchAndDevelopment|                           |


### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  occe: https://w3id.org/occe/
  dpv: https://w3id.org/dpv#
  obo: http://purl.obolibrary.org/obo/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]


  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:assigner, $(rule_assigner)]
      - [odrl:assignee, $(rule_assignee)]
      - p: odrl:action
        o:
          mapping: rule_action
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]


  rule_action: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [rdf:value, $(rule_action)~iri]
      - p: odrl:refinement
        o:
          mapping: rule_action_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Clinical Care

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit,rule_action_refinement_lo,rule_action_refinement_o,rule_action_refinement_ro,rule_action_refinement_unit
Agreement,https://example.com/policy:01,https://w3id.org/occe/,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/occe/ClinicalCare,
Agreement,https://example.com/policy:02,https://w3id.org/occe/,permission,odrl:read,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/occe/ClinicalCare,
```

|type     |uid                          |profile               |rule_type |rule_action|rule_assigner            |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro|rule_assignee_refinement_unit|rule_action_refinement_lo|rule_action_refinement_o|rule_action_refinement_ro         |rule_action_refinement_unit|
|---------|-----------------------------|----------------------|----------|-----------|-------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|---------------------------|-----------------------------|-------------------------|------------------------|----------------------------------|---------------------------|
|Agreement|https://example.com/policy:01|https://w3id.org/occe/|permission|odrl:use   |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/occe/ClinicalCare|                           |
|Agreement|https://example.com/policy:02|https://w3id.org/occe/|permission|odrl:read  |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/occe/ClinicalCare|                           |

### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  occe: https://w3id.org/occe/
  dpv: https://w3id.org/dpv#
  obo: http://purl.obolibrary.org/obo/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:assigner, $(rule_assigner)]
      - [odrl:assignee, $(rule_assignee)]
      - p: odrl:action
        o:
          mapping: rule_action
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [rdf:value, $(rule_action)~iri]
      - p: odrl:refinement
        o:
          mapping: rule_action_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Clinical Research

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit,rule_action_refinement_lo,rule_action_refinement_o,rule_action_refinement_ro,rule_action_refinement_unit
Agreement,https://example.com/policy:01,https://w3id.org/occe/,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/occe/ClinicalResearch,
Agreement,https://example.com/policy:02,https://w3id.org/occe/,permission,odrl:read,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,https://w3id.org/occe/ClinicalResearch,
```

|type     |uid                          |profile               |rule_type |rule_action|rule_assigner            |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro|rule_assignee_refinement_unit|rule_action_refinement_lo|rule_action_refinement_o|rule_action_refinement_ro             |rule_action_refinement_unit|
|---------|-----------------------------|----------------------|----------|-----------|-------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|---------------------------|-----------------------------|-------------------------|------------------------|--------------------------------------|---------------------------|
|Agreement|https://example.com/policy:01|https://w3id.org/occe/|permission|odrl:use   |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/occe/ClinicalResearch|                           |
|Agreement|https://example.com/policy:02|https://w3id.org/occe/|permission|odrl:read  |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |https://w3id.org/occe/ClinicalResearch|                           |

### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  occe: https://w3id.org/occe/
  dpv: https://w3id.org/dpv#
  obo: http://purl.obolibrary.org/obo/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:assigner, $(rule_assigner)]
      - [odrl:assignee, $(rule_assignee)]
      - p: odrl:action
        o:
          mapping: rule_action
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [rdf:value, $(rule_action)~iri]
      - p: odrl:refinement
        o:
          mapping: rule_action_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Disease Specific Use

### Data
```csv
type,uid,profile,rule_type,rule_action,rule_assigner,rule_assignee,rule_target,rule_assignee_refinement_lo,rule_assignee_refinement_o,rule_assignee_refinement_ro,rule_assignee_refinement_unit,rule_action_refinement_lo,rule_action_refinement_o,rule_action_refinement_ro,rule_action_refinement_unit
Agreement,https://example.com/policy:01,,permission,odrl:use,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,http://purl.obolibrary.org/obo/DOID_13921,
Agreement,https://example.com/policy:02,,permission,odrl:read,https://example.come/Sony,https://example.copm/user/1,https://example.copm/asset:01,,,,,odrl:purpose,odrl:isA,http://purl.obolibrary.org/obo/DOID_13922,
```

|type     |uid                          |profile|rule_type |rule_action|rule_assigner            |rule_assignee              |rule_target                  |rule_assignee_refinement_lo|rule_assignee_refinement_o|rule_assignee_refinement_ro|rule_assignee_refinement_unit|rule_action_refinement_lo|rule_action_refinement_o|rule_action_refinement_ro                |rule_action_refinement_unit|
|---------|-----------------------------|-------|----------|-----------|-------------------------|---------------------------|-----------------------------|---------------------------|--------------------------|---------------------------|-----------------------------|-------------------------|------------------------|-----------------------------------------|---------------------------|
|Agreement|https://example.com/policy:01|       |permission|odrl:use   |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |http://purl.obolibrary.org/obo/DOID_13921|                           |
|Agreement|https://example.com/policy:02|       |permission|odrl:read  |https://example.come/Sony|https://example.copm/user/1|https://example.copm/asset:01|                           |                          |                           |                             |odrl:purpose             |odrl:isA                |http://purl.obolibrary.org/obo/DOID_13922|                           |

### Model

```yaml
prefixes:
  odrl: http://www.w3.org/ns/odrl/2/
  xsd: http://www.w3.org/2001/XMLSchema#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  occe: https://w3id.org/occe/
  dpv: https://w3id.org/dpv#

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, odrl:$(type)]
      - [odrl:profile, $(profile)~iri]
      - p: odrl:$(rule_type)
        o:
          mapping: rule
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:target, $(rule_target)]
      - [odrl:assigner, $(rule_assigner)]
      - [odrl:assignee, $(rule_assignee)]
      - p: odrl:action
        o:
          mapping: rule_action
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [rdf:value, $(rule_action)~iri]
      - p: odrl:refinement
        o:
          mapping: rule_action_refinement
          condition:
            function: equal
            parameters:
              - [str1, $(uid)]
              - [str2, $(uid)]
              
  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: null
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```
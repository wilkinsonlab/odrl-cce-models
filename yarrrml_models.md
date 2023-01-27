## Use by Commercial Entity

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
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
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Geographical Area

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
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
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Regulatory Jurisdiction

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
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
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro)]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Research Use

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_action
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
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Clinical Care

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_action
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
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Clinical Research

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_action
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
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Disease Specific Use

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
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
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
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
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
    s: this:$(uniqid)_rule_action
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
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro)]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```
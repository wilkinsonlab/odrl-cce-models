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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [odrl:$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assignee, this:$(uniqid)_rule_assignee~iri]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_assignee_refinement~iri]

  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [odrl:$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assignee, this:$(uniqid)_rule_assignee~iri]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_assignee_refinement~iri]

  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [odrl:$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assignee, this:$(uniqid)_rule_assignee~iri]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_assignee_refinement~iri]

  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Use As Control

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:target, this:$(uniqid)_rule_target~iri]

  rule_target: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_target
    po:
      - [odrl:source, $(rule_target)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_target_refinement~iri]

  rule_target_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_target_refinement
    po:
      - [odrl:leftOperand, $(rule_target_refinement_lo)~iri]
      - [odrl:operator, $(rule_target_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_target_refinement_unit)~iri]
```

## Profit Motivated Use

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
  cc: http://creativecommons.org/ns#
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Time Period of Use

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Collaboration

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:duty, this:$(uniqid)_permission_duty~iri]

  permission_duty: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty
    po:
      - [odrl:action, this:$(uniqid)_permission_duty_action~iri]
      - [odrl:constraint, this:$(uniqid)_permission_duty_constraint~iri]

  permission_duty_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_action
    po:
      - [rdf:value, $(permission_duty_action)~iri]
      - [odrl:refinement, this:$(uniqid)_permission_duty_action_refinement~iri]

  permission_duty_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_action_refinement
    po:
      - [odrl:leftOperand, $(permission_duty_action_refinement_lo)~iri]
      - [odrl:operator, $(permission_duty_action_refinement_o)~iri]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_action_refinement_unit)~iri]

  permission_duty_constraint:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_constraint
    po:
      - [odrl:leftOperand, $(permission_duty_constraint_lo)~iri]
      - [odrl:operator, $(permission_duty_constraint_o)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_constraint_unit)~iri]
```

## Fees

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
  dbo: http://dbpedia.org/resource/
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:duty, this:$(uniqid)_permission_duty~iri]

  permission_duty: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty
    po:
      - [odrl:action, this:$(uniqid)_permission_duty_action~iri]
      - [odrl:constraint, this:$(uniqid)_permission_duty_constraint~iri]

  permission_duty_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_action
    po:
      - [rdf:value, $(permission_duty_action)~iri]
      - [odrl:refinement, this:$(uniqid)_permission_duty_action_refinement~iri]

  permission_duty_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_action_refinement
    po:
      - [odrl:leftOperand, $(permission_duty_action_refinement_lo)~iri]
      - [odrl:operator, $(permission_duty_action_refinement_o)~iri]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_action_refinement_unit)~iri]

  permission_duty_constraint:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_constraint
    po:
      - [odrl:leftOperand, $(permission_duty_constraint_lo)~iri]
      - [odrl:operator, $(permission_duty_constraint_o)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_constraint_unit)~iri]
```

## Return of Results

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
  dbo: http://dbpedia.org/resource/
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:duty, this:$(uniqid)_permission_duty~iri]

  permission_duty: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty
    po:
      - [odrl:action, $(permission_duty_action)~iri]
      - [odrl:constraint, this:$(uniqid)_permission_duty_constraint~iri]

  permission_duty_constraint:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_constraint
    po:
      - [odrl:leftOperand, $(permission_duty_constraint_lo)~iri]
      - [odrl:operator, $(permission_duty_constraint_o)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_constraint_unit)~iri]
```

## Return of Incidental Findings

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
  dbo: http://dbpedia.org/resource/
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:duty, this:$(uniqid)_permission_duty~iri]

  permission_duty: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty
    po:
      - [odrl:action, $(permission_duty_action)~iri]
      - [odrl:constraint, this:$(uniqid)_permission_duty_constraint~iri]

  permission_duty_constraint:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_constraint
    po:
      - [odrl:leftOperand, $(permission_duty_constraint_lo)~iri]
      - [odrl:operator, $(permission_duty_constraint_o)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_constraint_unit)~iri]
```

## (Re-)identification of individuals mediated by asset provider

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## (Re-)identification of individuals not mediated by asset provider

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

## Publication moratorium (pick 1 model based on data)

### Model (Constraint on assignee)

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [odrl:$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assignee, this:$(uniqid)_rule_assignee~iri]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_assignee_refinement~iri]

  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

### Model (Constraint on action)

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, this:$(uniqid)_rule_action~iri]

  rule_action: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action
    po:
      - [rdf:value, $(rule_action)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_action_refinement~iri]

  rule_action_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_action_refinement
    po:
      - [odrl:leftOperand, $(rule_action_refinement_lo)~iri]
      - [odrl:operator, $(rule_action_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_action_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_action_refinement_unit)~iri]
```

### Model (Constraint on target)

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:target, this:$(uniqid)_rule_target~iri]

  rule_target: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_target
    po:
      - [odrl:source, $(rule_target)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_target_refinement~iri]

  rule_target_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_target_refinement
    po:
      - [odrl:leftOperand, $(rule_target_refinement_lo)~iri]
      - [odrl:operator, $(rule_target_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_target_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_target_refinement_unit)~iri]
```

## Publication

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
  dbo: http://dbpedia.org/resource/
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:duty, this:$(uniqid)_permission_duty~iri]

  permission_duty: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty
    po:
      - [odrl:action, $(permission_duty_action)~iri]
      - [odrl:constraint, this:$(uniqid)_permission_duty_constraint~iri]

  permission_duty_constraint:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_permission_duty_constraint
    po:
      - [odrl:leftOperand, $(permission_duty_constraint_lo)~iri]
      - [odrl:operator, $(permission_duty_constraint_o)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(permission_duty_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(permission_duty_constraint_unit)~iri]
```

## User Authentication

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
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [odrl:$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:assignee, this:$(uniqid)_rule_assignee~iri]

  rule_assignee: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee
    po:
      - [a, odrl:Party]
      - [odrl:source, $(rule_assignee)~iri]
      - [odrl:refinement, this:$(uniqid)_rule_assignee_refinement~iri]

  rule_assignee_refinement:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_assignee_refinement
    po:
      - [odrl:leftOperand, $(rule_assignee_refinement_lo)~iri]
      - [odrl:operator, $(rule_assignee_refinement_o)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_dateTime), xsd:dateTime]
      - p: odrl:rightOperand
        o:
          function: grel:string_split
          parameters:
            - [grel:valueParameter, $(rule_assignee_refinement_ro_value_string)]
            - [grel:p_string_sep, "\|"]
          datatype: xsd:string
      - [odrl:rightOperand, $(rule_assignee_refinement_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_assignee_refinement_unit)~iri]
```

## Ethics Approval

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
  dbo: http://dbpedia.org/resource/
  this: https://example.com/

mappings:
  policy:
    sources:
      - [data.csv~csv]
    s: $(uid)
    po:
      - [a, $(type)~iri]
      - [odrl:uid, $(uid)~iri]
      - [odrl:profile, $(profile)~iri]
      - [$(rule_type), this:$(uniqid)_rule~iri]

  rule:
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule
    po:
      - [odrl:target, $(rule_target)~iri]
      - [odrl:assigner, $(rule_assigner)~iri]
      - [odrl:assignee, $(rule_assignee)~iri]
      - [odrl:action, $(rule_action)~iri]
      - [odrl:constraint, this:$(uniqid)_rule_constraint~iri]

  rule_constraint: 
    sources:
      - [data.csv~csv]
    s: this:$(uniqid)_rule_constraint
    po:
      - [odrl:leftOperand, $(rule_constraint_lo)~iri]
      - [odrl:operator, $(rule_constraint_o)~iri]
      - [odrl:rightOperand, $(rule_constraint_ro_value_iri)~iri]
      - [odrl:rightOperand, $(rule_constraint_ro_value_date), xsd:date]
      - [odrl:rightOperand, $(rule_constraint_ro_value_dateTime), xsd:dateTime]
      - [odrl:rightOperand, $(rule_constraint_ro_value_string), xsd:string]
      - [odrl:rightOperand, $(rule_constraint_ro_value_float), xsd:float]
      - [odrl:unit, $(rule_constraint_unit)~iri]
```
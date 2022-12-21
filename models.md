# Use by Commercial Entity

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    { "obo": "http://purl.obolibrary.org/obo/" }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0001",
  "permission": [
    {
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "assigner": "http://example.com/owner:181",
      "assignee": {
        "@type": "PartyCollection",
        "source": "http://example.com/entities",
        "refinement": [
          {
            "leftOperand": "odrl:industry",
            "operator": "odrl:eq",
            "rightOperand": "obo:ICO_0000049"
          }
        ]
      }
    }
  ],
  "prohibition": [
    {
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "assigner": "http://example.com/owner:181",
      "assignee": {
        "@type": "PartyCollection",
        "source": "http://example.com/entities",
        "refinement": [
          {
            "leftOperand": "odrl:industry",
            "operator": "odrl:eq",
            "rightOperand": "obo:ICO_0000048"
          }
        ]
      }
    }
  ]
}
```

---

# Geographical area

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "dbo": "http://dbpedia.org/ontology/",
      "wgs84_pos": "http://www.w3.org/2003/01/geo/wgs84_pos#"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0002",
  "permission": [
    {
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "assigner": "http://example.com/owner:181",
      "assignee": {
        "@type": "PartyCollection",
        "source": "http://example.com/entities",
        "refinement": {
          "xone": {
            "@list": [
              { "@id": "http://example.com/policy:0002/C1" },
              { "@id": "http://example.com/policy:0002/C2" }
            ]
          }
        }
      }
    }
  ]
}

{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "wgs84_pos": "http://www.w3.org/2003/01/geo/wgs84_pos#",
      "rdfs": "http://www.w3.org/2000/01/rdf-schema#"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0002/C1",
  "leftOperand": "odrl:spatial",
  "operator": "odrl:isPartOf",
  "rightOperand": { "@value": ["wgs84_pos:Point", "wgs84_pos:Point", "...", "wgs84_pos:Point"], "@type": "rdfs:list" }
}

{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "dbo": "http://dbpedia.org/ontology/"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0002/C2",
  "leftOperand": "odrl:spatialCoordinates",
  "operator": "odrl:eq",
  "rightOperand": "dbo:iso31661Code"
}
```

---

# Regulatory Jurisdiction

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "fibo-fnd-law-jur": "https://spec.edmcouncil.org/fibo/ontology/FND/Law/Jurisdiction/",
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0003",
  "profile": "occe:",
  "permission": [
    {
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "assigner": "http://example.com/owner:181",
      "assignee": {
        "@type": "PartyCollection",
        "source": "http://example.com/entities",
        "refinement": [
          {
            "leftOperand": "occe:jurisdiction",
            "operator": "odrl:isA",
            "rightOperand": "fibo-fnd-law-jur:Jurisdiction"
          }
        ]
      }
    }
  ]
}
```

# Research Use

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "dpv": "https://w3id.org/dpv#"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0004",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": [
            {
              "leftOperand": "odrl:purpose",
              "operator": "odrl:isA",
              "rightOperand": "dpv:ResearchAndDevelopment"
            }
          ]
        }
      ]
    }
  ]
}
```

# Clinical Care

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0005",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": [
            {
              "leftOperand": "occe:purpose",
              "operator": "odrl:isA",
              "rightOperand": "occe:ClinicalCare"
            }
          ]
        }
      ]
    }
  ]
}
```

# Clinical Research

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0006",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": [
            {
              "leftOperand": "occe:purpose",
              "operator": "odrl:isA",
              "rightOperand": "occe:ClinicalResearch"
            }
          ]
        }
      ]
    }
  ]
}
```

# Disease specific use

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "obo": "http://purl.obolibrary.org/obo/",
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0007",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": [
            {
              "leftOperand": "odrl:purpose",
              "operator": "odrl:isA",
              "rightOperand": "obo:DOID_4"
            }
          ]
        }
      ]
    }
  ]
}
```

# Use as control

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "obo": "http://purl.obolibrary.org/obo/",
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0008",
  "profile": "occe:",
  "permission": [
    {
      "action": "odrl:read",
      "assigner": "http://example.com/owner:181",
      "target": {
        "@type": "AssetCollection",
        "source": "http://example.com/assets",
        "refinement": [
          {
            "leftOperand": "occe:useAs",
            "operator": "odrl:eq",
            "rightOperand": "obo:NCIT_C48294"
          }
        ]
      }
    }
  ]
}
```

# Profit motivated use

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "obo": "http://purl.obolibrary.org/obo/",
      "cc": "http://creativecommons.org/ns#"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0009",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "cc:CommercialUse" },
          "refinement": [
            {
              "leftOperand": "odrl:purpose",
              "operator": "odrl:isA",
              "rightOperand": "obo:ICO_0000057"
            }
          ]
        }
      ]
    }
  ]
}
```

# Time period of use

Constraints will be evaluated in sequence and must be both fulfilled.

```json
{
  "@context": "https://www.w3.org/ns/odrl.jsonld",
  "@type": "Offer",
  "uid": "http://example.com/policy:0010",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": {
            "andSequence": {
              "@list": [
                { "@id": "http://example.com/policy:0002/C1" },
                { "@id": "http://example.com/policy:0002/C2" }
              ]
            }
          }
        }
      ]
    }
  ]
}

// Start datetime constraint
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "xsd": "http://www.w3.org/2001/XMLSchema#"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0010/C1",
  "leftOperand": "odrl:dateTime",
  "operator": "odrl:eq", // Or lt, lteq, gt, gteq
  "rightOperand": {
    "@value": "some_date_or_datetime",
    "@type": "xsd:date" // Or xsd:dateTime
  }
}

// End datetime constraint
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "xsd": "http://www.w3.org/2001/XMLSchema#"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0010/C2",
  "leftOperand": "odrl:dateTime",
  "operator": "odrl:eq", // Or lt, lteq, gt, gteq
  "rightOperand": {
    "@value": "some_date_or_datetime",
    "@type": "xsd:date" // Or xsd:dateTime
  }
}
```

# Collaboration

The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and must collaborate with the assigner or any other party (right operand value). The duty also has a constraint of `event` is equal to `policyUsage`, meaning the duty rule must be exercised (ie the collaboration) while the permission rule is exercised.

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0011",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "duty": [
        {
          "action": [
            {
              "rdf:value": { "@id": "occe:collaborate" },
              "refinement": [
                {
                  "leftOperand": "odrl:recipient",
                  "operator": "odrl:eq",
                  "rightOperand": "http://example.com/owner:181"
                }
              ]
            }
          ],
          "constraint": [
            {
              "leftOperand": "event",
              "operator": "odrl:eq",
              "rightOperand": { "@id": "odrl:policyUsage" }
            }
          ]
        }
      ]
    }
  ]
}
```

# Fees

The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and must compensate the assigner or any other party (right operand value) by paying an amount of money in euro. The duty also has a constraint of `event` is less than `policyUsage`, meaning the duty rule must be exercised (ie the collaboration) before the permission rule can be exercised.

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0012",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "duty": [
        {
          "action": [
            {
              "rdf:value": { "@id": "odrl:compensate" },
              "refinement": [
                {
                  "leftOperand": "odrl:payAmount",
                  "operator": "odrl:eq",
                  "rightOperand": {
                    "@value": "any_decimal_value",
                    "@type": "xsd:decimal"
                  },
                  "unit": "http://dbpedia.org/resource/Euro"
                }
              ]
            }
          ],
          "constraint": [
            {
              "leftOperand": "event",
              "operator": "odrl:lt",
              "rightOperand": { "@id": "odrl:policyUsage" }
            }
          ]
        }
      ]
    }
  ]
}
```

# Return of results

The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and involves a requirement on the recipient (assignee) to return incidental findings to the asset provider (assigner). The duty also has a constraint of `event` is greater than `policyUsage`, meaning the duty rule must be exercised (ie the return of results) after the permission rule has been exercised.

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0013",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "duty": [
        {
          "action": "occe:returnOfResults",
          "constraint": [
            {
              "leftOperand": "event",
              "operator": "odrl:gt",
              "rightOperand": { "@id": "odrl:policyUsage" }
            }
          ]
        }
      ]
    }
  ]
}
```

# Return of incidental findings

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0014",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "duty": [
        {
          "action": "occe:returnOfIncidentalFindings",
          "constraint": [
            {
              "leftOperand": "event",
              "operator": "odrl:gt",
              "rightOperand": { "@id": "odrl:policyUsage" }
            }
          ]
        }
      ]
    }
  ]
}
```

# Re-identification of individuals

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0015",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": [
            {
              "leftOperand": "odrl:purpose",
              "operator": "odrl:isA",
              "rightOperand": "occe:ReIdentificationOfIndividuals"
            }
          ]
        }
      ]
    }
  ]
}
```

# Publication moratorium

We can't create a generic policy for this CCE because there can be **many** constraints that could be applied to actions, assets or assignees.

```json
{
  "@context": "https://www.w3.org/ns/odrl.jsonld",
  "@type": "Offer",
  "uid": "http://example.com/policy:0016",
  "permission": [],
  "prohibition": [],
  "obligation": []
}
```

# Publication

The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and involves a requirement on the recipient (assignee) to publish the results. The duty also has a constraint of `event` is greater than `policyUsage`, meaning the duty rule must be exercised (ie the publication of results) after the permission rule has been exercised.

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0017",
  "profile": "occe:",
  "permission": [
    {
      "assigner": "http://example.com/owner:181",
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "duty": [
        {
          "action": "occe:publishResults",
          "constraint": [
            {
              "leftOperand": "event",
              "operator": "odrl:gt",
              "rightOperand": { "@id": "odrl:policyUsage" }
            }
          ]
        }
      ]
    }
  ]
}
```

# User authentication

A permission where the constraint (refinement) is applied on the assignee to check if its ID is one of the provided IDs (right operand).

```json
{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/",
      "rdfs": "http://www.w3.org/2000/01/rdf-schema#"
    }
  ],
  "@type": "Offer",
  "uid": "http://example.com/policy:0018",
  "profile": "occe:",
  "permission": [
    {
      "target": "http://example.com/dataset:1212",
      "action": "odrl:use",
      "assigner": "http://example.com/owner:181",
      "assignee": {
        "@type": "PartyCollection",
        "source": "http://example.com/users",
        "refinement": [
          {
            "leftOperand": "occe:userID",
            "operator": "odrl:isPartOf",
            "rightOperand": {
              "@value": ["email_1", "ORCID_2", "...n"],
              "@type": "rdfs:list"
            }
          }
        ]
      }
    }
  ]
}
```

# Ethics Approval

A permission where a logical constraint is applied on the action to check if the document is an Institutional Review Board Approval and if the industry of the approval body is the Institutional Review Board.

```json
{
  "@context": "https://www.w3.org/ns/odrl.jsonld",
  "@type": "Offer",
  "uid": "http://example.com/policy:0019",
  "permission": [
    {
      "target": "http://example.com/dataset:1212",
      "assigner": "http://example.com/owner:181",
      "assignee": ,
      "action": [
        {
          "rdf:value": { "@id": "odrl:use" },
          "refinement": {
            "andSequence": {
              "@list": [
                { "@id": "http://example.com/policy:0019/C1" },
                { "@id": "http://example.com/policy:0019/C2" }
              ]
            }
          }
        }
      ]
    }
  ]
}

{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/",
      "obo": "http://purl.obolibrary.org/obo/"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0019/C1",
  "leftOperand": "occe:documentType",
  "operator": "odrl:isA",
  "rightOperand": "obo:NCIT_C70800"
}

{
  "@context": [
    "https://www.w3.org/ns/odrl.jsonld",
    {
      "occe": "https://w3id.org/odrl-occe/",
      "obo": "http://purl.obolibrary.org/obo/"
    }
  ],
  "@type": "Constraint",
  "uid": "http://example.com/policy:0019/C2",
  "leftOperand": "odrl:industry",
  "operator": "odrl:isA",
  "rightOperand": "obo:NCIT_C16741"
}
```

```yml
obo: <http://purl.obolibrary.org/obo/>

- Use by Commercial Entity:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: assignee
      odrl:industry eq obo:ICO_0000049 (profit organization)
  PROHIBITION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: assignee
      odrl:industry eq obo:ICO_0000048 (nonprofit organization)
```

```yml
wgs84_pos: <http://www.w3.org/2003/01/geo/wgs84_pos#>
dbo: <http://dbpedia.org/ontology/>

- Geographical area:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: assignee
      xone:
        @list: [this:constraintSpatial, this:constraintSpatialCoordinates]

  constraintSpatial:
    leftOperand: odrl:spatial
    operator: odrl:isPartOf
    rightOperand: [wgs84_pos:Point, wgs84_pos:Point, ...wgs84_pos:Point]^^rdfs:list (A point, typically described using a coordinate system relative to Earth, such as WGS84, uniquely identified by lat/long/alt)

  constraintSpatialCoordinates:
    leftOperand: odrl:spatialCoordinates
    operator: odrl:eq
    rightOperand: dbo:iso31661Code (ISO 3166-1 country code)
```

```yml
fibo-fnd-law-jur: <https://spec.edmcouncil.org/fibo/ontology/FND/Law/Jurisdiction/>
occe: <https://w3id.org/odrl-occe/>

- Regulatory Jurisdiction:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: assignee
      occe:jurisdiction isA fibo-fnd-law-jur:Jurisdiction (power of a court to adjudicate cases, issue orders, and interpret and apply the law with respect to some specific geographic area)
```

```yml
dpv: <https://w3id.org/dpv#>

- Research Use:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA dpv:ResearchAndDevelopment
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Clinical care:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA occe:ClinicalCare
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Clinical Research:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA occe:ClinicalResearch
```

```yml
obo: <http://purl.obolibrary.org/obo/>
occe: <https://w3id.org/odrl-occe/>

- Disease specific use:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA obo:DOID_4 (A disease is a disposition to undergo pathological processes that exists in an organism because of one or more disorders in that organism.)
```

```yml
obo: <http://purl.obolibrary.org/obo/>
occe: <https://w3id.org/odrl-occe/>

- Use as control:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:read
    assigner: data center
    CONSTRAINT:
      on: asset
      occe:useAs eq obo:NCIT_C48294 (Something referred to; the object of a reference.)
```

```yml
cc: <http://creativecommons.org/ns#>
obo: <http://purl.obolibrary.org/obo/>

- Profit motivated use:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: cc:CommercialUse
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA obo:ICO_0000057 (An investigation that is conducted with the purpose of earning a profit)
```

```yml
- Time period of use:
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      refinement:
        andSequence:
          @list: [this:start_date, this:end_date]

  start_date:
    type: Constraint
    uid: this:start_date
    leftOperand: odrl:dateTime
    operator: lt | lteq | eq | gt | gteq
    rightOperand: xsd:date | xsd:dateTime

  end_date:
    type: Constraint
    uid: this:end_date
    leftOperand: odrl:dateTime
    operator: lt | lteq | eq | gt | gteq
    rightOperand: xsd:date | xsd:dateTime
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Collaboration:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    duty:
      action:
        rdf:value:
          @id: occe:collaborate
        refinement:
          leftOperand: odrl:recipient
          operator: eq
          rightOperand: this:assigner
```

```yml
occe: <https://w3id.org/odrl-occe/>
dbo: <https://dbpedia.org/ontology/>

- Fees:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    duty:
      action:
        rdf:value:
          @id: odrl:compensate
        refinement:
          leftOperand: odrl:payAmount
          operator: eq
          rightOperand:
            @value: "any_decimal_value"
            @type: xsd:decimal
          unit: dbo:currency
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Return of results:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    duty:
      action: occe:returnOfResults
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Return of incidental findings:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    duty:
      action: occe:returnOfIncidentalFindings
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Re-identification of individuals:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      odrl:purpose isA occe:ReIdentificationOfIndividuals
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Publication moratorium:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: occe:publishResults
    assigner: data center
    CONSTRAINT:
      on: depends on the conditions
      refinement:
          andSequence:
            @list: [this:C1, this:C2, ...this:C<n>]

  C1:
    type: Constraint
    uid: this:C1
    leftOperand: odrl:someLeftOperand
    operator: odrl:someOperator
    rightOperand: odrl:someRightOperand

  C2:
    type: Constraint
    uid: this:C2
    leftOperand: odrl:someLeftOperand
    operator: odrl:someOperator
    rightOperand: odrl:someRightOperand
```

```yml
occe: <https://w3id.org/odrl-occe/>

- Publication:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    duty:
      action: occe:publishResults
```

```yml
rdfs: <http://www.w3.org/2000/01/rdf-schema#>
occe: <https://w3id.org/odrl-occe/>

- User authentication:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: assignee
      occe:userID isPartOf ["email_1", "ORCID_2", ...n]^^rdfs:list
```

```yml
obo: <http://purl.obolibrary.org/obo/>
occe: <https://w3id.org/odrl-occe/>

- Ethics Approval:
  profile: occe
  type: Offer
  PERMISSION:
    target: ex:dataset
    action: odrl:use
    assigner: data center
    CONSTRAINT:
      on: action
      refinement:
          andSequence:
            @list: [this:approvalDocumentType, this:approvedByIRB]

  approvalDocumentType:
    type: Constraint
    uid: this:approvalDocumentType
    leftOperand: occe:documentType
    operator: odrl:isA
    rightOperand: obo:NCIT_C70800 (A document containing the determination of the Institutional Review Board (IRB) that the clinical study with human subject participation has been reviewed and may be conducted at a particular study site within the constraints set forth by the IRB and other institutional and federal requirements.)

  approvedByIRB:
    type: Constraint
    uid: this:approvedByIRB
    leftOperand: odrl:industry
    operator: odrl:isA
    rightOperand: obo:NCIT_C16741 (An independent body constituted of medical, scientific, and non-scientific members, whose responsibility is to ensure the protection of the rights, safety and well-being of human subjects involved in a study by, among other things, reviewing, approving, and providing continuing review of study protocol and amendments and of the methods and material to be used in obtaining and documenting informed consent of the study subjects.)
```

- Commercial Entity - Should be applied to the Party(assignee), as we need to check its industry (i.e: Profit organization or Nonprofit organization).

---

- Geographic Area - Should be applied to the assignee Party, as a geographical restriction is imposed to the application of the policy. The assignee must operate on the specified region(s). We can use odrl:spatial for World Geodetic System (WGS84) Point values OR odrl:spatialCoordonates for ISO 3166-1 codes. We are using a logical constraint with xone operand, which means that ONE and ONLY ONE of the constraints (constraintSpatial, constraintSpatialCoordinates) must be satisfied.

---

- Regulatory Jurisdiction - Should be applied to the assignee Party as the assignee must operate in a geopolitical area covered by a jurisdiction. We use the Foundations (FND) ontology from Financial Industry Business Ontology (FIBO). The jurisdiction is adapted from (https://www.law.cornell.edu/wex/jurisdiction)[https://www.law.cornell.edu/wex/jurisdiction].

---

- Research Use - Should be applied to the action, as we want to know its purpose.

---

- Clinical Care - Should be applied to the action itself as the use action is permitted only for a specific purpose. We use the newly created occe:ClinicalCare right operand.

---

- Clinical Research - Same as above. But we use the newly created occe:ClinicalResearch right operand.

---

- Disease Specific use - Same as above. We are using obo:DOID_4 as right operand to represent all diseases.

---

- Use as control - Should be applied to the asset as it will be used as a reference, benchmark or normal comparison for research or other activities. The action should be `odrl:read` because as said before, asset will be used **only** as a reference (we try to be specific).

---

- Profit motivated use - Should be applied to the action as we need to check the purpose of the action (which is to earn money). We don't use odrl:sell because it implies to transfer the ownership of the asset to the assignee, which is not the definition of this CCE. We don't use odrl:use because ODRL offers cc:CommercialUse action, so it's better to be specific.

---

- Time period of use - We should apply a logical constraint on the action. The logical constraint will proceed in sequence (which means that both constraints (start_data and end_date) -in sequence- **MUST** be satisfied).

---

- Collaboration - We apply a duty that must be fulfilled by the assignee toward the assigner. The duty implies a newly created action `occe:collaborate`. In the constraint, we use the `odrl:recipient` left operand because, by definition, it's "The party receiving the result/outcome of exercising the action of the Rule."

---

- Fees - We apply a duty that must be fulfilled by the assignee toward the assigner. The duty implies to compensate the assigner by paying fees. The amount of compensation is a decimal value and the unit is any subclass of dbo:currency.

---

- Return of results - The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and involves a requirement on the recipient (assignee) to return the results to the asset provider (assigner). The duty also has a constraint of `event` is greater (because results are obtained after the work is done) than `policyUsage`, meaning the duty rule must be exercised (ie the return of results) after the permission rule has been exercised. We use a newly created action `occe:returnOfResults`.

---

- Return of incidental findings - The assigner makes an offer to use the target asset. The assignee who wants to use them has a duty and involves a requirement on the recipient (assignee) to return incidental findings to the asset provider (assigner). The duty also has a constraint of `event` is greater (because results are obtained after the work is done) than `policyUsage`, meaning the duty rule must be exercised (ie the return of incidental findings) after the permission rule has been exercised.

---

- Re-identification of individuals - We apply a constraint on the action as they want/need to identify individuals in an anonymised or pseudonymised asset (which is its purpose) using the new `occe:permitUsePurpose` left operand.

---

- Publication moratorium - We can't create a generic policy for this CCE because there can be **many** constraints that could be applied to actions, assets or assignees.

---

- Publication - To use the asset(s), the assignee Party **MUST** publish the results of studies using those same asset(s) provided by the assigner Party.

---

- User authentication - We apply a constraint on the assignee Party where it checks that the user ID (ORCID or email address) is included in a set of IDs. We use the newly created left operand `occe:userID`.

---

- Ethics Approval - We apply a logical constraint on the assignee Party. The logical constraint will proceed in sequence (which means that all constraints -in sequence- **MUST** be satisfied). The constraints must be: check the type of the document provided (which **MUST** be of type `obo:NCIT_C70800`) and the approval body (which **MUST** be of type `obo:NCIT_C16741`).

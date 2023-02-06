## General Glossary for any CCE

- **type**: Policy type, one of the following:
  - Set
  - Offer
  - Agreement
- **uid**: Policy unique identifier (ex: https://example.com/policy:01)
- **profile** (OPTIONAL): A custom ODRL profile to use (ex: https://example.com/my_custom_odrl_profile)
- **rule_type**: Rule type, one of the following:
  - Permission
  - Prohibition
  - Duty (through the `obligation` property)
- **rule_target**: Rule target (ex: https://example.com/asset)
- **rule_assigner**: The assigner of the rule (ex: https://example.com/Apple)
- **rule_assignee**: The assignee of the rule (ex: https://example.com/Apple)
- **rule_action**: Rule action (ex: http://www.w3.org/ns/odrl/2/use)
- **rule_action_refinement_lo** (OPTIONAL): Left operand of the refinement of the action of the rule
- **rule_action_refinement_o** (OPTIONAL): Operator of the refinement of the action of the rule
- **rule_action_refinement_ro_value_iri** (OPTIONAL): Right operand of the refinement of the action of the rule as IRI type
- **rule_action_refinement_ro_value_date** (OPTIONAL): Right operand of the refinement of the action of the rule as Date datatype
- **rule_action_refinement_ro_value_dateTime** (OPTIONAL): Right operand of the refinement of the action of the rule as DateTime datatype
- **rule_action_refinement_ro_value_string** (OPTIONAL): Right operand of the refinement of the action of the rule as String datatype
- **rule_action_refinement_ro_value_float** (OPTIONAL): Right operand of the refinement of the action of the rule as Float datatype
- **rule_action_refinement_unit** (OPTIONAL): Unit of the refinement of the action of the rule
- **rule_target_refinement_lo** (OPTIONAL): Left operand of the refinement of the target of the rule
- **rule_target_refinement_o** (OPTIONAL): Operator of the refinement of the target of the rule
- **rule_target_refinement_ro_value_iri** (OPTIONAL): Right operand of the refinement of the target of the rule as IRI type
- **rule_target_refinement_ro_value_date** (OPTIONAL): Right operand of the refinement of the target of the rule as Date datatype
- **rule_target_refinement_ro_value_dateTime** (OPTIONAL): Right operand of the refinement of the target of the rule as DateTime datatype
- **rule_target_refinement_ro_value_string** (OPTIONAL): Right operand of the refinement of the target of the rule as String datatype
- **rule_target_refinement_ro_value_float** (OPTIONAL): Right operand of the refinement of the target of the rule as Float datatype
- **rule_target_refinement_unit** (OPTIONAL): Unit of the refinement of the target of the rule
- **rule_assignee_refinement_lo** (OPTIONAL): Left operand of the refinement of the assignee of the rule
- **rule_assignee_refinement_o** (OPTIONAL): Operator of the refinement of the assignee of the rule
- **rule_assignee_refinement_ro_value_iri** (OPTIONAL): Right operand of the refinement of the assignee of the rule as IRI type
- **rule_assignee_refinement_ro_value_date** (OPTIONAL): Right operand of the refinement of the assignee of the rule as Date datatype
- **rule_assignee_refinement_ro_value_dateTime** (OPTIONAL): Right operand of the refinement of the assignee of the rule as DateTime datatype
- **rule_assignee_refinement_ro_value_string** (OPTIONAL): Right operand of the refinement of the assignee of the rule as String datatype
- **rule_assignee_refinement_ro_value_float** (OPTIONAL): Right operand of the refinement of the assignee of the rule as Float datatype
- **rule_assignee_refinement_unit** (OPTIONAL): Unit of the refinement of the assignee of the rule
- **rule_constraint_lo** (OPTIONAL): Left operand of the constraint of the rule
- **rule_constraint_o** (OPTIONAL): Operator of the constraint of the rule
- **rule_constraint_ro_value_iri** (OPTIONAL): Right operand of the constraint of the rule as IRI type
- **rule_constraint_ro_value_date** (OPTIONAL): Right operand of the constraint of the rule as Date datatype
- **rule_constraint_ro_value_dateTime** (OPTIONAL): Right operand of the constraint of the rule as DateTime datatype
- **rule_constraint_ro_value_string** (OPTIONAL): Right operand of the constraint of the rule as String datatype
- **rule_constraint_ro_value_float** (OPTIONAL): Right operand of the constraint of the rule as Float datatype
- **rule_constraint_unit** (OPTIONAL): Unit of the action of the duty of the permission
- **permission_duty_target** (OPTIONAL): The target of the permission duty (ex: https://example.com/assets_2)
- **permission_duty_action** (OPTIONAL): The action of the permission duty (ex: http://www.w3.org/ns/odrl/2/compensate)
- **permission_duty_action_refinement_lo** (OPTIONAL): Left operand of the action of the duty of the permission
- **permission_duty_action_refinement_o** (OPTIONAL): Operator of the action of the duty of the permission
- **permission_duty_action_refinement_ro_value_iri** (OPTIONAL): Right operand of the action of the duty of the permission as IRI type
- **permission_duty_action_refinement_ro_value_date** (OPTIONAL): Right operand of the action of the duty of the permission as Date datatype
- **permission_duty_action_refinement_ro_value_dateTime** (OPTIONAL): Right operand of the action of the duty of the permission as DateTime datatype
- **permission_duty_action_refinement_ro_value_string** (OPTIONAL): Right operand of the action of the duty of the permission as String datatype
- **permission_duty_action_refinement_ro_value_float** (OPTIONAL): Right operand of the action of the duty of the permission as Float datatype
- **permission_duty_action_refinement_unit** (OPTIONAL): Unit of the right operand action of the duty of the permission
- **permission_duty_constraint_lo** (OPTIONAL): Left operand of the constraint of the duty of the permission
- **permission_duty_constraint_o** (OPTIONAL): Operator of the constraint of the duty of the permission
- **permission_duty_constraint_ro_value_iri** (OPTIONAL): Right operand of the constraint of the duty of the permission as IRI type
- **permission_duty_constraint_ro_value_date** (OPTIONAL): Right operand of the constraint of the duty of the permission as Date datatype
- **permission_duty_constraint_ro_value_dateTime** (OPTIONAL): Right operand of the constraint of the duty of the permission as DateTime datatype
- **permission_duty_constraint_ro_value_string** (OPTIONAL): Right operand of the constraint of the duty of the permission as String datatype
- **permission_duty_constraint_ro_value_float** (OPTIONAL): Right operand of the constraint of the duty of the permission as Float datatype
- **permission_duty_constraint_unit** (OPTIONAL): Unit of the right operand of the constraint of the duty of the permission
- **prohibition_remedy_action** (OPTIONAL): The action of the remedy of the prohibition
- **prohibition_remedy_target** (OPTIONAL): The target of the remedy of the prohibition
- **uniqid**: A numeric ID for the Policy to avoid the use of blank nodes in generated RDF

## CCE - Use by Commercial Entity

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement_lo**: Any http://www.w3.org/ns/odrl/2/leftOperand
- **rule_assignee_refinement_o**: Any http://www.w3.org/ns/odrl/2/operator
- **rule_assignee_refinement_ro_value_iri**: Any value (ex: http://purl.obolibrary.org/obo/ICO_0000049)
- **rule_assignee_refinement_ro_value_date**: Any value
- **rule_assignee_refinement_ro_value_string**: Any value
- **rule_assignee_refinement_ro_value_float**: Any value

## CCE - Geographical Area

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/spatialCoordinates
- **rule_assignee_refinement_o**: ex: (http://www.w3.org/ns/odrl/2/eq for equality or http://www.w3.org/ns/odrl/2/neq for inequality)
- **rule_assignee_refinement_ro_value_iri**: ISO 3166-1 country code (https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/ES)
- **rule_assignee_refinement_ro_value_string**: Any value (`ES`)

## CCE - Regulatory Jurisdiction

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement_lo**: ex: https://w3id.org/occe/jurisdiction
- **rule_assignee_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA
- **rule_assignee_refinement_ro_value_iri**: ex: Instance of fibo-fnd-law-jur:Jurisdiction (ex: https://spec.edmcouncil.org/fibo/ontology/BE/GovernmentEntities/NorthAmericanJurisdiction/CAGovernmentEntitiesAndJurisdictions/)
- **rule_assignee_refinement_ro_value_string**: Any value (ex: Any name of jurisdiction)

## CCE - Research Use

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA or http://www.w3.org/ns/odrl/2/eq or http://www.w3.org/ns/odrl/2/neq
- **rule_action_refinement_ro_value_iri**: ex: https://w3id.org/dpv#ResearchAndDevelopment
- **rule_action_refinement_ro_value_string**: ex: `R&D`

## CCE - Clinical Care

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA or http://www.w3.org/ns/odrl/2/eq or http://www.w3.org/ns/odrl/2/neq
- **rule_action_refinement_ro_value_iri**: ex: https://w3id.org/dpv#ClinicalCare
- **rule_action_refinement_ro_value_string**: ex: `Clinical care`

## CCE - Clinical Research

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA or http://www.w3.org/ns/odrl/2/eq or http://www.w3.org/ns/odrl/2/neq
- **rule_action_refinement_ro_value_iri**: ex: https://w3id.org/dpv#ClinicalResearch
- **rule_action_refinement_ro_value_string**: ex: `Clinical research`

## CCE - Disease Specific Use

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA or http://www.w3.org/ns/odrl/2/eq
- **rule_action_refinement_ro_value_iri**: ex: http://purl.obolibrary.org/obo/DOID_13921
- **rule_action_refinement_ro_value_string**: ex: `Alzheimer`

## CCE - Use As Control

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/read
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_target_refinement_lo**: ex: https://w3id.org/occe/useAs
- **rule_target_refinement_o**: ex: http://www.w3.org/ns/odrl/2/eq
- **rule_target_refinement_ro_value_iri**: ex: http://purl.obolibrary.org/obo/NCIT_C48294
- **rule_target_refinement_ro_value_string**: ex: `Reference`

## CCE - Profit Motivated Use

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://creativecommons.org/ns#CommercialUse
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA
- **rule_action_refinement_ro_value_iri**: ex: http://purl.obolibrary.org/obo/ICO_0000057
- **rule_action_refinement_ro_value_string**: ex: `Profit motivated use`

## CCE - Time Period of Use

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/dateTime
- **rule_action_refinement_o**: ex: (one of http://www.w3.org/ns/odrl/2/lt, http://www.w3.org/ns/odrl/2/lteq, http://www.w3.org/ns/odrl/2/gt and http://www.w3.org/ns/odrl/2/gteq)
- **rule_action_refinement_ro_value_date**: ex: Any xsd:date value: 2020-12-31
- **rule_action_refinement_ro_value_dateTime**: ex: Any xsd:dateTime value: 2017-12-31T06:00Z

## CCE - Collaboration

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **permission_duty_action**: ex: https://w3id.org/occe/collaborate
- **permission_duty_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/recipient
- **permission_duty_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/eq
- **permission_duty_action_refinement_ro**: http://example.com/owner:181
- **permission_duty_constraint_lo**: ex: http://www.w3.org/ns/odrl/2/event
- **permission_duty_constraint_o**: ex: http://www.w3.org/ns/odrl/2/eq
- **permission_duty_constraint_ro_value_iri**: http://www.w3.org/ns/odrl/2/policyUsage

## CCE - Fees

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **permission_duty_action**: ex: http://www.w3.org/ns/odrl/2/compensate
- **permission_duty_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/payAmount
- **permission_duty_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/eq
- **permission_duty_action_refinement_ro**: 500.00
- **permission_duty_action_refinement_unit**: ex: http://dbpedia.org/resource/Euro
- **permission_duty_constraint_lo**: ex: http://www.w3.org/ns/odrl/2/event
- **permission_duty_constraint_o**: ex: http://www.w3.org/ns/odrl/2/lt
- **permission_duty_constraint_ro_value_iri**: ex: http://www.w3.org/ns/odrl/2/policyUsage

## CCE - Return of Results

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **permission_duty_action**: ex: https://w3id.org/occe/returnOfResults
- **permission_duty_constraint_lo**: ex: http://www.w3.org/ns/odrl/2/event
- **permission_duty_constraint_o**: ex: http://www.w3.org/ns/odrl/2/gt
- **permission_duty_constraint_ro_value_iri**: http://www.w3.org/ns/odrl/2/policyUsage

## CCE - Return of Incidental Findings

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **permission_duty_action**: ex: https://w3id.org/occe/returnOfIncidentalFindings
- **permission_duty_constraint_lo**: ex: http://www.w3.org/ns/odrl/2/event
- **permission_duty_constraint_o**: ex: http://www.w3.org/ns/odrl/2/gt
- **permission_duty_constraint_ro_value_iri**: http://www.w3.org/ns/odrl/2/policyUsage

## CCE - Re-identification of Individuals

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_action_refinement_lo**: ex: http://www.w3.org/ns/odrl/2/purpose
- **rule_action_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isA
- **rule_action_refinement_ro**: ex: https://w3id.org/occe/ReIdentificationOfIndividuals

## CCE - Publication moratorium

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **ALL OTHER FIELDS ARE POSSIBLE**

## CCE - Publication

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **permission_duty_action**: ex: https://w3id.org/occe/publishResults
- **permission_duty_constraint_lo**: ex: http://www.w3.org/ns/odrl/2/event
- **permission_duty_constraint_o**: ex: http://www.w3.org/ns/odrl/2/gt
- **permission_duty_constraint_ro_value_iri**: http://www.w3.org/ns/odrl/2/policyUsage

## CCE - User Authentication

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement_lo**: ex: https://w3id.org/occe/userID
- **rule_assignee_refinement_o**: ex: http://www.w3.org/ns/odrl/2/isPartOf
- **rule_assignee_refinement_ro_value_iri**: ex: http://example.com/list_of_users_ids
- **rule_assignee_refinement_ro_value_string**: ex: `5408498|310155|905094|2501484`

## CCE - Ethics Approval

- **type**: ex: `Offer`
- **uid**: https://example.com/policy:01
- **profile**: https://w3id.org/occe/
- **rule_type**: ex: `Permission`
- **rule_action**: ex: http://www.w3.org/ns/odrl/2/use
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_constraint_lo**: ex: https://w3id.org/occe/documentType
- **rule_constraint_o**: ex: http://www.w3.org/ns/odrl/2/isA
- **rule_constraint_ro_value_iri**: ex: http://purl.obolibrary.org/obo/NCIT_C70800
- **rule_constraint_ro_value_string**: ex: `Institutional Review Board Approval`

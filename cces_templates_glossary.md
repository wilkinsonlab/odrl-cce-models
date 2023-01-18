## General Glossary for any CCE

- **type**: Policy type, one of the following:
  - [http://www.w3.org/ns/odrl/2/Set](http://www.w3.org/ns/odrl/2/Set)
  - [http://www.w3.org/ns/odrl/2/Offer](http://www.w3.org/ns/odrl/2/Offer)
  - [http://www.w3.org/ns/odrl/2/Agreement](http://www.w3.org/ns/odrl/2/Agreement)
- **uid**: Policy unique identifier (ex: https://example.com/policy:01)
- **profile** (OPTIONAL): A custom ODRL profile to use (ex: https://example.com/my_custom_odrl_profile)
- **rule_type**: Rule type, one of the following:
  - http://www.w3.org/ns/odrl/2/Permission
  - http://www.w3.org/ns/odrl/2/Prohibition
  - http://www.w3.org/ns/odrl/2/Duty (through the `obligation` property)
- **rule_action**: Rule action (ex: odrl:use)
- **rule_action_refinement** (OPTIONAL): Boolean to indicate that the rule's action has a refinement (defaults to `false`)
- **rule_action_refinement_lo** (OPTIONAL): Left operand of the refinement of the action of the rule (**ONLY** if `rule_action_refinement` = `true`)
- **rule_action_refinement_o** (OPTIONAL): Operator of the refinement of the action of the rule (**ONLY** if `rule_action_refinement` = `true`)
- **rule_action_refinement_ro** (OPTIONAL): Right operand of the refinement of the action of the rule (**ONLY** if `rule_action_refinement` = `true`)
- **rule_target**: Rule target (ex: https://example.com/asset)
- **rule_target_refinement**: Boolean to indicate that the rule's target has a refinement (defaults to `false`)
- **rule_target_refinement_lo** (OPTIONAL): Left operand of the refinement of the target of the rule (**ONLY** if `rule_target_refinement` = `true`)
- **rule_target_refinement_o** (OPTIONAL): Operator of the refinement of the target of the rule (**ONLY** if `rule_target_refinement` = `true`)
- **rule_target_refinement_ro** (OPTIONAL): Right operand of the refinement of the target of the rule (**ONLY** if `rule_target_refinement` = `true`)
- **rule_assigner**: The assigner of the rule (ex: https://example.com/Apple)
- **rule_assignee**: The assignee of the rule (ex: https://example.com/Apple)
- **rule_assignee_refinement**: Boolean to indicate that the rule's assignee has a refinement (defaults to `false`)
- **rule_assignee_refinement_lo** (OPTIONAL): Left operand of the refinement of the assignee of the rule (**ONLY** if `rule_assignee_refinement` = `true`)
- **rule_assignee_refinement_o** (OPTIONAL): Operator of the refinement of the assignee of the rule (**ONLY** if `rule_assignee_refinement` = `true`)
- **rule_assignee_refinement_ro** (OPTIONAL): Right operand of the refinement of the assignee of the rule (**ONLY** if `rule_assignee_refinement` = `true`)
- **rule_constraint**: Boolean to indicate that the rule has a constraint (defaults to `false`)
- **rule_constraint_lo** (OPTIONAL): Left operand of the constraint of the rule (**ONLY** if `rule_constraint` = `true`)
- **rule_constraint_o** (OPTIONAL): Operator of the constraint of the rule (**ONLY** if `rule_constraint` = `true`)
- **rule_constraint_ro** (OPTIONAL): Right operand of the constraint of the rule (**ONLY** if `rule_constraint` = `true`)
- **rule_constraint_unit** (OPTIONAL): Right operand of the action of the duty of the permission (**ONLY** if `rule_constraint` = `true`)
- **permission_duty_target** (OPTIONAL): The target of the permission duty (ex: https://example.com/assets_2)
- **permission_duty_action** (OPTIONAL): The action of the permission duty (ex: odrl:compensate)
- **permission_duty_action_refinement**: Boolean to indicate that the permission duty action has a refinement (defaults to `false`)
- **permission_duty_action_refinement_lo** (OPTIONAL): Left operand of the action of the duty of the permission (**ONLY** if `permission_duty_action_refinement` = `true`)
- **permission_duty_action_refinement_o** (OPTIONAL): Operator of the action of the duty of the permission (**ONLY** if `permission_duty_action_refinement` = `true`)
- **permission_duty_action_refinement_ro** (OPTIONAL): Right operand of the action of the duty of the permission (**ONLY** if `permission_duty_action_refinement` = `true`)
- **permission_duty_action_refinement_unit** (OPTIONAL): Unit of the right operand action of the duty of the permission (**ONLY** if `permission_duty_action_refinement` = `true`)
- **permission_duty_constraint**: Boolean to indicate that the permission duty has a constraint (defaults to `false`)
- **permission_duty_constraint_lo** (OPTIONAL): Left operand of the constraint of the duty of the permission (**ONLY** if `permission_duty_constraint` = `true`)
- **permission_duty_constraint_o** (OPTIONAL): Operator of the constraint of the duty of the permission (**ONLY** if `permission_duty_constraint` = `true`)
- **permission_duty_constraint_ro** (OPTIONAL): Right operand of the constraint of the duty of the permission (**ONLY** if `permission_duty_constraint` = `true`)
- **permission_duty_constraint_unit** (OPTIONAL): Unit of the right operand of the constraint of the duty of the permission (**ONLY** if `permission_duty_constraint` = `true`)
- **prohibition_remedy**: Boolean to indicate that the prohibition rule has a remedy (defaults to `false`)
- **prohibition_remedy_action** (OPTIONAL): The action of the remedy of the prohibition (**ONLY** if `prohibition_remedy` = `true`)
- **prohibition_remedy_target** (OPTIONAL): The target of the remedy of the prohibition (**ONLY** if `prohibition_remedy` = `true`)

## CCE - Use by Commercial Entity

- **type**: Offer
- **uid**: https://example.com/policy:01
- **rule_type**: Permission
- **rule_action**: `odrl:use`
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement**: `true`
- **rule_assignee_refinement_lo**: Any `odrl:leftOperand`
- **rule_assignee_refinement_o**: Any `odrl:operator`
- **rule_assignee_refinement_ro**: Any right operand (ex: https://example.com/some_URI)

## CCE - Geographical Area

- **type**: Offer
- **uid**: https://example.com/policy:01
- **rule_type**: Permission
- **rule_action**: `odrl:use`
- **rule_target**: https://example.com/asset
- **rule_assigner**: https://example.com/Apple
- **rule_assignee**: https://example.com/user
- **rule_assignee_refinement**: `true`
- **rule_assignee_refinement_lo**: `odrl:leftOperand` should be `odrl:spatialCoordinates`
- **rule_assignee_refinement_o**: `odrl:operator` (should be `odrl:eq` for equality or `odrl:neq` for inequality)
- **rule_assignee_refinement_ro**: ISO 3166-1 country code

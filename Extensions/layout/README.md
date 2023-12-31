# CACAO Layout Specification Version 1.0

The [CACAO Layout specification](https://docs.oasis-open.org/cacao/layout/v1.0/csd01/layout-v1.0-csd01.html) defines the CACAO Layout Extension for the purpose of visually representing CACAO playbooks consistently across implementations.

The specification defines one Extension Definition (as defined in section 5 of the specification) for CACAO Playbooks and has the following identifier: `extension-definition--418ee24c-9cb1-46d9-afa5-309e01aabc7f`  


## JSON Validation Schemas

The JSON validation schemas are available in the [schemas directory](./schemas/).

## CACAO Playbook with Layout - Example

The complete example encorporating the CACAO Layout specification can be found here: [CACAO playbook with Layout extension](./examples/playbook--aa1898b6-5251-49b4-aeb7-fd5e912583ff.json).

## Breaking Down the Example

### 1. Providing the Extension Definition

The `extension_definitions` property at the playbook (metadata) level, holds all the extensions utilized in the current playbook. In this case, we provide the CACAO Layout Extension Definition object. 

```JSON
"extension_definitions": {
  "type": "extension-definition",
  "name": "CACAO Layout",
  "description": "Extension definition for diagramming CACAO playbooks.",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "schema": "https://github.com/oasis-tcs/cacao/tree/master/Extensions/layout/schemas/layout.json",
  "version": "1.0.0",
  "external_references": [
    {
      "name": "CACAO Layout Specification.",
      "description": "Specification for diagramming CACAO Playbooks graphically.",
      "source": "[CACAO-Layout-Schema-v1.0] CACAO Layout Schema Version 1.0. Edited by Vasileios Mavroeidis and Mateusz Zych. 12 December 2023. OASIS Committee Specification Draft 01. https://docs.oasis-open.org/cacao/layout/v1.0/csd01/layout-v1.0-csd01.html. Latest version: https://docs.oasis-open.org/cacao/layout/v1.0/layout-v1.0.html.",
      "url": "https://docs.oasis-open.org/cacao/layout/v1.0/layout-v1.0.html"
    }
  ]
}
```

### 2. Use the Canvas Property

The `playbook_extensions` property at the playbook (metadata) level is used to extend the playbook object (metadata) itself as per Section 3.1 in the CACAO specification [CACAO-Security-Playbooks-v2.0](https://docs.oasis-open.org/cacao/security-playbooks/v2.0/security-playbooks-v2.0.html)).
We are using this property to define the canvas size for the visualized playbook through the `canvas` property of the CACAO Layout extension.

```JSON
"playbook_extensions": {
  "extension-definition--418ee24c-9cb1-46d9-afa5-309e01aabc7f": {
    "type": "layout",
    "canvas": {
      "width": 1300,
      "height": 800
    }
  }
}
```

### 3. Use the Coordinates Property

The CACAO Coordinates Property can be used in all Workflow Steps, and Agent and Targets objects.

#### 3.1 Switch Conditional Step

The code snippet below, presents the extension of a workflow step, in particular the switch conditional workflow step, through the `step_extension` property using the `coordinates` property of the CACAO Layout Extension.

```JSON
"switch-condition--72c55a11-5091-4714-8050-baa854d72eda": {
  "type": "switch-condition",
  "name": "switch case example",
  "cases": {
    "1": "action--4005472a-0b74-48c6-b04b-45bb8cf2b1ae",
    "2": "action--63483dce-6122-4975-8c7c-795d2453243d",
    "default": "action--9a4ef680-ba51-4c1b-9b2d-715caf06ef3a"
  },
  "on_completion": "action--9ae9e500-155e-4f63-a76e-a43856063f55",
  "step_extensions": {
    "extension-definition--418ee24c-9cb1-46d9-afa5-309e01aabc7f": {
      "type": "layout",
      "coordinates": {
        "x": 690,
        "y": 440,
        "outgoing_connections": [
        {
          "connection_type": "on-completion",
          "x": [810, 900],
          "y": [470, 470]
        },
        {
          "connection_type": "cases",
          "x": [750, 750, 900],
          "y": [500, 540, 540],
          "case": "1"
        },
        {
          "connection_type": "cases",
          "x": [750, 750, 900],
          "y": [500, 610, 610],
          "case": "2"
        },
        {
          "connection_type": "cases",
          "x": [750, 750, 900],
          "y": [500, 690, 690],
          "case": "default"
        }
        ]
      }
    }
  }
}
```

#### 3.2 Action Step

Action step utilizing the Coordinates property of the CACAO Layout extension with a simple straight line connection to the next construct.

```JSON
"action--9ae9e500-155e-4f63-a76e-a43856063f55": {
  "type": "action",
  "name": "Action step after Switch condition",
  "on_completion": "end--b09eaa5d-9d96-4315-a071-d08414cde0ca",
  "step_extensions": {
    "extension-definition--418ee24c-9cb1-46d9-afa5-309e01aabc7f": {
        "type": "layout",
        "coordinates": {
          "x": 900,
          "y": 440,
          "outgoing_connections": [
          {
            "connection_type": "on-completion",
            "x": [1050, 1150],
            "y": [470, 470]
          }
        ]
      }
    }
  }
}
```

#### 3.3 End Step

End step utilizing the Coordinates property of the CACAO Layout extension without outgoing connections.

```JSON
"end--b09eaa5d-9d96-4315-a071-d08414cde0ca": {
  "type": "end",
  "name": "End of playbook.",
  "step_extensions": {
    "extension-definition--418ee24c-9cb1-46d9-afa5-309e01aabc7f": {
      "type": "layout",
      "coordinates": {
        "x": 1150,
        "y": 450
      }
    }
  }
}
```

## Resources

- [CACAO-Coordinates-Schema-v1.0]
CACAO Layout Extension Version 1.0. Edited by Vasileios Mavroeidis and Mateusz Zych. 22 December 2023. OASIS Committee Specification Draft 01. [https://docs.oasis-open.org/cacao/layout/v1.0/csd01/layout-v1.0-csd01.html]. Latest version: [https://docs.oasis-open.org/cacao/layout/v1.0/layout-v1.0.html].
- [CACAO-Security-Playbooks-v2.0]
CACAO Security Playbooks Version 2.0. Edited by Bret Jordan and Allan Thomson. 27 November 2023. OASIS Committee Specification 01. [https://docs.oasis-open.org/cacao/securityplaybooks/v2.0/cs01/security-playbooks-v2.0-cs01.html]. Latest version: [https://docs.oasisopen.org/cacao/security-playbooks/v2.0/security-playbooks-v2.0.html].

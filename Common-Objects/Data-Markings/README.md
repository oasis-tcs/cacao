# Common Data Markings

The following Data Markings are the official versions to be used with CACAO playbooks.

## TLPv2

The following standard data marking definitions **MUST** be used to represent
`TLP:RED`, `TLP:AMBER`, `TLP:AMBER+STRICT`, `TLP:GREEN`, and `TLP:CLEAR` TLP
markings.

### TLP:CLEAR

marking-tlp--94868c89-83c2-464b-929b-a1a8aa3c8487

```json
{
  "marking-tlp--94868c89-83c2-464b-929b-a1a8aa3c8487": {
    "type": "marking-tlp",
    "id": "marking-tlp--94868c89-83c2-464b-929b-a1a8aa3c8487",
    "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
    "created": "2022-10-01T00:00:00.000Z",
    "tlpv2_level": "TLP:CLEAR"
  }
}
```

### TLP:GREEN

marking-tlp--bab4a63c-aed9-4cf5-a766-dfca5abac2bb

```json
{
  "marking-tlp--bab4a63c-aed9-4cf5-a766-dfca5abac2bb": {
    "type": "marking-tlp",
    "id": "marking-tlp--bab4a63c-aed9-4cf5-a766-dfca5abac2bb",
    "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
    "created": "2022-10-01T00:00:00.000Z",
    "tlpv2_level": "TLP:GREEN"
  }
}
```

### TLP:AMBER

marking-tlp--55d920b0-5e8b-4f79-9ee9-91f868d9b421

```json
{
  "marking-tlp--55d920b0-5e8b-4f79-9ee9-91f868d9b421": {
    "type": "marking-tlp",
    "id": "marking-tlp--55d920b0-5e8b-4f79-9ee9-91f868d9b421",
    "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
    "created": "2022-10-01T00:00:00.000Z",
    "tlpv2_level": "TLP:AMBER"
  }
}
```

### TLP:AMBER+STRICT

marking-tlp--939a9414-2ddd-4d32-a0cd-375ea402b003

```json
{
  "marking-tlp--939a9414-2ddd-4d32-a0cd-375ea402b003": {
    "type": "marking-tlp",
    "id": "marking-tlp--939a9414-2ddd-4d32-a0cd-375ea402b003",
    "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
    "created": "2022-10-01T00:00:00.000Z",
    "tlpv2_level": "TLP:AMBER+STRICT"
  }
}
```

### TLP:RED

marking-tlp--e828b379-4e03-4974-9ac4-e53a884c97c1

```json
{
  "marking-tlp--e828b379-4e03-4974-9ac4-e53a884c97c1": {
    "type": "marking-tlp",
    "id": "marking-tlp--e828b379-4e03-4974-9ac4-e53a884c97c1",
    "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
    "created": "2022-10-01T00:00:00.000Z",
    "tlpv2_level": "TLP:RED"
  }
}
```

## All TLP Marking Definitions 

This is all of the TLP marking definitions in a CACAO `data_marking_definitions` property.

```json
{
  "data_marking_definitions": {
    "marking-tlp--94868c89-83c2-464b-929b-a1a8aa3c8487": {
      "type": "marking-tlp",
      "id": "marking-tlp--94868c89-83c2-464b-929b-a1a8aa3c8487",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2022-10-01T00:00:00.000Z",
      "tlpv2_level": "TLP:CLEAR"
    },
    "marking-tlp--bab4a63c-aed9-4cf5-a766-dfca5abac2bb": {
      "type": "marking-tlp",
      "id": "marking-tlp--bab4a63c-aed9-4cf5-a766-dfca5abac2bb",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2022-10-01T00:00:00.000Z",
      "tlpv2_level": "TLP:GREEN"
    },
    "marking-tlp--55d920b0-5e8b-4f79-9ee9-91f868d9b421": {
      "type": "marking-tlp",
      "id": "marking-tlp--55d920b0-5e8b-4f79-9ee9-91f868d9b421",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2022-10-01T00:00:00.000Z",
      "tlpv2_level": "TLP:AMBER"
    },
    "marking-tlp--939a9414-2ddd-4d32-a0cd-375ea402b003": {
      "type": "marking-tlp",
      "id": "marking-tlp--939a9414-2ddd-4d32-a0cd-375ea402b003",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2022-10-01T00:00:00.000Z",
      "tlpv2_level": "TLP:AMBER+STRICT"
    },
    "marking-tlp--e828b379-4e03-4974-9ac4-e53a884c97c1": {
      "type": "marking-tlp",
      "id": "marking-tlp--e828b379-4e03-4974-9ac4-e53a884c97c1",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2022-10-01T00:00:00.000Z",
      "tlpv2_level": "TLP:RED"
    }
  }
}
```
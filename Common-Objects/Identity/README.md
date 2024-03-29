# Common Identity Objects

The following official STIX v2.1 Identity objects are used in various places
within the CACAO playbooks specification. They are provided here to help
implementations.

## OASIS Open

identity--8ce3f695-d5a4-4dc8-9e93-a65af453a31a

```json
{
  "type": "identity",
  "spec_version": "2.1",
  "id": "identity--8ce3f695-d5a4-4dc8-9e93-a65af453a31a",
  "created": "2021-03-13T20:09:20.8889Z",
  "modified": "2023-06-20T10:00:00.000Z",
  "name": "OASIS Open",
  "description": "OASIS is a global community of experts who drive the creation and adoption of open standards promoting interoperability, innovation, and freedom of choice.",
  "roles": [ "Standards Developing Organization (SDO)" ],
  "identity_class": "organization",
  "sectors": [ "non-profit" ],
  "contact_information": "info@oasis-open.org"
}
```

## CACAO Technical Committee

identity--5abe695c-7bd5-4c31-8824-2528696cdbf1

```json
{
  "type": "identity",
  "spec_version": "2.1",
  "id": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created_by_ref": "identity--8ce3f695-d5a4-4dc8-9e93-a65af453a31a",
  "created": "2023-06-20T10:00:00.000Z",
  "modified": "2023-06-20T10:00:00.000Z",
  "name": "OASIS Collaborative Automated Course of Action Operations (CACAO) for Cyber Security TC",
  "description": "A global community of cyber security experts creating standards enabling increased automation, collaboration, and effectiveness of the global response to cyber threats.",
  "roles": [ "Technical Committee" ],
  "identity_class": "organization",
  "sectors": [ "non-profit" ],
  "contact_information": "cacao-comment@lists.oasis-open.org"
}
```
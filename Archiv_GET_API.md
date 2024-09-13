# Get Archive by ID

##/api/Archive/{archiveguid}

Ruft Informationen über ein bestimmtes Archiv anhand seiner eindeutigen Kennung ab.

### Headers

- Content-Type: application/json
- Authorization: Bearer <token>

### Body Parameter

- name (string): Name des Benutzers.
- age (number): Alter des Benutzers.

### Response

- 200 OK: Erfolgreich Archivdetails abgerufen.
  ```json
  {
    "id": "1",
    "name": "John",
    "age": 30
  }

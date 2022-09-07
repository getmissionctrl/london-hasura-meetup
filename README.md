# london-hasura-meetup
Code from the London Hasura talent platform workshop

## Resources

### Retool app
https://getmissionctrl.retool.com/editor/Talent%20Lifecycle

### n8n

Code: https://github.com/getmissionctrl/hasrua-workshop-n8n

Railway: https://hasura-workshop-n8n.up.railway.app/workflow

### Hasura

Console: https://cloud.hasura.io/project/a8fb35d0-ea09-4b4f-9338-cc5c8bc75a90/console

Endpoint: https://hasura-workshop.missionctrl.dev/v1/graphql

### Schema

```mermaid
erDiagram
    COMPANY {
        int id PK
        string name
        string sector
    }
    TALENTPARTNER {
        string name
        string email
    }
    ROLE-STATUS {
        string status
        string description
    }
    ROLE-TYPE {
        string type
        string description
    }
    ROLE {
        int id
        string company
        string department
        string role-type
        string status
        string owner
        date start-date
        data created
    }
    CANDIDATE {
        string productCode
        int quantity
        float pricePerUnit
    }
    COMPANY ||--o{ ROLE : roles
    TALENTPARTNER ||--o{ COMPANY : working-with
    TALENTPARTNER ||--o{ ROLE : owner
    ROLE ||--o| ROLE-TYPE : type
    ROLE ||--o| ROLE-STATUS : status
    CANDIDATE ||--o{ ROLE : appying-for
```

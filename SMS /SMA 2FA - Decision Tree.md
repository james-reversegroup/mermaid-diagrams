flowchart TD
    start[Need SMS/2FA?]
    altAuth{Alternative 2FA Available?}
    critical{Is Service Critical?}
    serviceType{Type of Service?}
    shared{Is Account Shared?}
    region{Which Region?}
    useAlt[Use Alternative 2FA]
    noPhone[Do Not Use Shared Phone]
    usPhone[Use US Number]
    euPhone[Use EU Number]

    start --> altAuth
    altAuth -->|Yes| useAlt
    altAuth -->|No| critical
    critical -->|No| noPhone
    critical -->|Yes| serviceType
    
    serviceType -->|Purchase Alerts| region
    serviceType -->|Marketing| noPhone
    serviceType -->|Account 2FA| shared
    
    shared -->|No| noPhone
    shared -->|Yes| critical
    
    region -->|US| usPhone
    region -->|EU| euPhone

    style start fill:#f9f,stroke:#333,stroke-width:4px
    style usPhone fill:#bbf,stroke:#333,stroke-width:2px
    style euPhone fill:#bbf,stroke:#333,stroke-width:2px
    style noPhone fill:#fcc,stroke:#333,stroke-width:2px
    style useAlt fill:#cfc,stroke:#333,stroke-width:2px

```marmaid

flowchart TD
    start[Need IT Support?]
    urgent{Is it Urgent?}
    template{Type of Request?}
    access[Use /request Command]
    password[Password Reset Process]
    issue[Technical Issue Process]
    setup[New Setup Process]
    waiting[Support Response]
    resolved{Issue Resolved?}
    complete[Mark Complete ✅]
    continue[Continue in Thread]
    
    start --> urgent
    urgent -->|Yes| high[Use @urgent-it Template]
    urgent -->|No| standard[Use Standard Template]
    
    high --> template
    standard --> template
    
    template -->|Access| access
    template -->|Password| password
    template -->|Technical| issue
    template -->|Setup| setup
    
    access --> waiting
    password --> waiting
    issue --> waiting
    setup --> waiting
    
    waiting --> resolved
    resolved -->|Yes| complete
    resolved -->|No| continue
    continue --> waiting
    
    style start fill:#f9f,stroke:#333,stroke-width:4px
    style complete fill:#cfc,stroke:#333,stroke-width:2px
    style urgent fill:#fcf,stroke:#333,stroke-width:2px
    style template fill:#fcf,stroke:#333,stroke-width:2px
    style resolved fill:#fcf,stroke:#333,stroke-width:2px

```

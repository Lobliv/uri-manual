# Annex: Process Flowchart

This section provides a high-level visual representation of the lifecycle of a Unified Requirement (UR) within the URI Platform, tracking actions taken by both the Secretariat and individual Member Societies.

```mermaid
flowchart TD
    A[Adopted UR] --> B1[Secretariat publishes UR on URI]

    B1 --> B2[Member Society reviews applicability]

    B2 --> C{UR applicable? <br>C5.1.1.4.4}

    C -- No --> C1[Set status N/A and enter reason in URI]
    C1 --> Z[URI notifies GPG and Secretariat]

    C -- Yes --> D{Implementation issue? <br>C5.1.1.4}

    %% No implementation issue
    D -- No --> K{Remove previous reservation?}
    K -- Yes -->K1[Withdraw previous Reservation, C5.1.1.6]
    K1 --> D1
    D1[Status set to Compliance in URI, C5.1.1.4.1]

    K -- No -->D1

    D1 --> Z

    %% Implementation issues exist
    D -- Yes --> F{Reason for issue}

    F -- Unsuitable UR --> G1[Declare reservation <br>C5.1.1.4.2]
    F -- Internal rules cycle --> G2[Postponement declared <br>C5.1.1.4.3]

    G1 --> H1[Status set to Partly or Full Reservation]
    G2 --> H2[Status set to Full Reservation]

    H1 --> I[Maintain Action Plan in URI]
    H2 --> I

    I --> J[Update Actions Complete field]
    J --> Z
    %% J --> K{Reservation removed?}

    %% K -- Yes --> Z1[Withdraw Reservation in URI]
    %% Z1 --> Z
    %% K -- No --> L[Monitor]

    %% L -- Yes --> M[Withdraw reservation on common implementation date]
    %% L -- No --> Z

    %% M --> N[Update status to Implemented]
    %% N --> Z

    Z[URI notifies GPG and Secretariat]

    Z --> Y[Biannual Report produced for GPG meeting and Annual summary published on IACS website]
```
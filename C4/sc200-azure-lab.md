## System Context diagram

### Test lab scenario used for studying Microsoft SC-200 certification

```mermaid
C4Context
    title System Context Diagram for SC-200 Cloud Lab
    Person(user, "Administrator")
    Boundary(b0, "sc200-testlab-rg", "resource group") {
        Boundary(b1, "aulab-vnet", "virtual network") {
        System(SystemA, "autestdc-01", "domain controller")
        System(SystemB, "autestpc-01", "client")
        }
    }

    Rel(user, SystemA, "uses", "RDP")
    Rel(user, SystemB, "uses", "RDP")
    Rel(SystemB, SystemA, "Uses", "LDAP, RDP")

    UpdateRelStyle(user, SystemA, $textColor="orange", $lineColor="orange", $offsetX="-55", $offsetY="-70")
    UpdateRelStyle(user, SystemB, $textColor="orange", $lineColor="orange", $offsetX="-72", $offsetY="-70")

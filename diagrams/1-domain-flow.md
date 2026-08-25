
``` mermaid
graph TB
	U[User] --> P[Products]
	U --> I[Invoices]
	
	P -- Inventory Entry --> B@{ shape: fork, label: "Join" }
	I -- Create / Edit --> B
	
	B --> Issue@{ shape: text, label: "Issue Invoice" }
	
	Issue --> Inventory@{ shape: text, label: "Update Inventory" }
	
	Inventory --> Final@{ shape: text, label: "Finalized Invoice" }
	
```

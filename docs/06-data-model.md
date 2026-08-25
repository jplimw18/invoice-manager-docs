# Data Model

## Entities

### Product:

- Identity
- Unique Identifier (Domain)
- Description
-  Registration Date
### Invoice:

- Identity
- Sequential Number (Domain)
- Status (Open/Finalized)
  
*A **product** can appears in many **Invoices** and one **invoice** can have many **products** , so**
### Invoice Item: (Product < n : n > Invoice)

- Identity
- ***Product***
- ***Invoice***
- Quantity
  
*Invetory is a **sum of inputs and outputs** of a product, I think*

### Inventory: (Product < 1 : n > Inventory)

- Identity
- ***Product***
- Input/Output
- Payload
- Creation Date
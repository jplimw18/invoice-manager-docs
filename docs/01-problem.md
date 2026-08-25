# Problem

## Context

The system manages products, inventory, and invoices.

Products must exist before they can be included in invoices. Products have an available stock balance that is affected by inventory movements.

Invoices contain products and their respective quantities. An invoice starts as `Open` and can be finalized/issued. During issuance, the system verifies product availability and performs the corresponding inventory movement.

The system also provides visibility into inventory movements and current stock.

## Actors

### User

The main actor interacting with the system.

The user can:

- Register products;
    
- Manage inventory entries;
    
- Create and edit invoices;
    
- Finalize invoices;
    
- View products;
    
- Monitor inventory movements.
    

## Capabilities

### Product Management

- Register products;
    
- Identify products through a unique code;
    
- View product information;
    
- View current stock;
    
- Access inventory movement history.
    

### Inventory Management

- Register inventory entries;
    
- Update product stock;
    
- Record inventory movements;
    
- Monitor inventory movements;
    
- Filter movements by product, date, volume, entries, and exits.
    

### Invoice Management

- Create invoices;
    
- Generate sequential invoice numbers;
    
- Add products and quantities;
    
- Edit open invoices;
    
- View invoices;
    
- Finalize/issue invoices.
    

### Invoice Issuance

- Validate product availability;
    
- Perform inventory transactions;
    
- Finalize the invoice.
    

## Core Flow

```text
Register Product
      ↓
Initial Inventory Entry
      ↓
Create Invoice
      ↓
Add Products + Quantities
      ↓
Open Invoice
      ↓
Issue / Finalize Invoice
      ↓
Validate Inventory
      ↓
Inventory Movement
      ↓
Finalized Invoice
```

## Scope

The system currently covers:

- Product registration;
    
- Product visualization;
    
- Inventory entries;
    
- Inventory monitoring;
    
- Invoice registration;
    
- Invoice visualization;
    
- Invoice editing while open;
    
- Invoice issuance/finalization;
    
- Inventory updates resulting from invoice issuance.
# Domain

## Entities

### Product

Represents a product that can be stored in inventory and included in invoices.

Relevant information:

- Unique product code;
    
- Description;
    
- Current stock balance;
    
- Registration date.
    

### Invoice

Represents a document containing products that are intended to be issued.

Relevant information:

- Sequential number;
    
- Status;
    
- Products;
    
- Quantities.
    

An invoice starts as `Open` and can become `Finalized`.

### Invoice Item

Represents a product and its quantity within an invoice.

An invoice contains one or more invoice items.

### Inventory Movement

Represents a change in the stock balance of a product.

Movements can represent:

- Entries;
    
- Exits.
    

Inventory movements are used to maintain the stock balance and provide a history of changes.

## Relationships

```text
Product
   │
   ├───────────────┐
   │               │
   ▼               ▼
Inventory      Invoice Item
Movement           │
                   ▼
                Invoice
```

- A product can have multiple inventory movements.
    
- An invoice contains multiple invoice items.
    
- Each invoice item refers to a product.
    
- Invoice issuance creates inventory movements for its products.
    

## States

### Invoice

```text
Open
  │
  │ Issue / Finalize
  ▼
Finalized
```

An `Open` invoice can be modified.

A `Finalized` invoice cannot be issued again.

## Domain Events

The current model identifies the following meaningful events:

- Product registered;
    
- Inventory entry registered;
    
- Invoice created;
    
- Invoice modified;
    
- Invoice issued/finalized;
    
- Inventory movement registered.
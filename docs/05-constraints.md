# Constraints

## Consistency

Invoice issuance involves both the invoice state and inventory state.

The system should avoid situations where:

- An invoice is finalized without its inventory being updated.
    
- Inventory is updated without the invoice being properly finalized.
    

## Inventory

Stock must represent the result of the inventory movements performed by the system.

The system must prevent an invoice from consuming unavailable inventory.

## Concurrency

The system must account for situations where multiple operations attempt to consume the same available inventory simultaneously.

Example:

```text
Product stock = 1

Invoice A → consumes 1
Invoice B → consumes 1
```

The system must preserve a valid inventory state.

## Repeated Operations

Invoice issuance may be requested more than once.

Repeated requests must not cause the same inventory to be consumed multiple times.

## Failure

The system must account for failures during operations involving:

- Product registration;
    
- Inventory transactions;
    
- Invoice registration;
    
- Invoice issuance.
    

A failure must not leave the business state inconsistent.

## Monitoring

Inventory movements should be observable through a monitoring interface with filtering capabilities for:

- Product;
    
- Date;
    
- Volume;
    
- Entries;
    
- Exits.
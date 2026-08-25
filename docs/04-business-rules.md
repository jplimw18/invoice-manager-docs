# Business Rules

## Product

- A product must have a unique code.
    
- A product must exist before it can be included in an invoice.
    
- A product has an associated stock balance.
    

## Inventory

- Inventory movements modify the stock balance.
    
- Inventory movements can represent entries or exits.
    
- Stock availability must be considered when issuing an invoice.
    

## Invoice

- Every invoice has a sequential number.
    
- Every invoice starts as `Open`.
    
- An invoice contains products and quantities.
    
- An `Open` invoice can be modified.
    
- A finalized invoice cannot be modified.
    
- A finalized invoice cannot be issued again.
    

## Invoice Issuance

- Only an `Open` invoice can be issued.
    
- Product availability must be validated before issuance.
    
- Issuing an invoice consumes the corresponding product quantities.
    
- Successful issuance results in a finalized invoice.
    
- Insufficient inventory prevents the invoice from being finalized.
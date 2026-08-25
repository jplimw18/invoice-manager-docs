# Use Cases

## UC001 — Register Product

**Actor:** User

**Goal:** Register a product and its initial stock.

### Main Flow

1. User provides product information.
    
2. System verifies the product code.
    
3. User provides the initial stock balance.
    
4. System registers the product.
    
5. System registers the initial inventory entry.
    

### Exceptions

- Product code already exists.
    
- Product information is invalid.
    
- Product registration fails.
    
- Initial inventory entry fails.
    

---

## UC002 — View Product

**Actor:** User

**Goal:** View product information and inventory state.

### Main Flow

1. User selects a product.
    
2. System displays product information.
    
3. System displays the current stock balance.
    
4. System provides access to inventory movement history.
    

### Exceptions

- Product does not exist.
    
- Product information cannot be retrieved.
    

---

## UC003 — Register Inventory Entry

**Actor:** User

**Goal:** Increase the available stock of a product.

### Main Flow

1. User selects a product.
    
2. User provides the quantity to add.
    
3. System validates the quantity.
    
4. System registers the inventory movement.
    
5. System updates the stock balance.
    

### Exceptions

- Invalid quantity.
    
- Inventory transaction fails.
    

---

## UC004 — Create Invoice

**Actor:** User

**Goal:** Create an invoice containing products and quantities.

### Main Flow

1. System generates a sequential invoice number.
    
2. User selects products.
    
3. User defines quantities.
    
4. System registers the invoice as `Open`.
    

### Exceptions

- Invoice registration fails.
    

---

## UC005 — View Invoice

**Actor:** User

**Goal:** View existing invoices and their details.

### Main Flow

1. User accesses the invoice list.
    
2. System displays invoices.
    
3. User can filter invoices.
    
4. User selects an invoice.
    
5. System displays its details.
    

### Exceptions

- Invoice cannot be retrieved.
    

---

## UC006 — Modify Invoice

**Actor:** User

**Goal:** Modify an invoice before it is finalized.

### Main Flow

1. User selects an `Open` invoice.
    
2. User modifies its products or quantities.
    
3. System validates the changes.
    
4. System saves the invoice.
    

### Exceptions

- Invoice is already finalized.
    
- Invalid invoice data.
    
- Modification fails.
    

---

## UC007 — Issue Invoice

**Actor:** User

**Goal:** Finalize an invoice and apply its inventory effects.

### Main Flow

1. User selects an `Open` invoice.
    
2. User confirms issuance.
    
3. System validates product availability.
    
4. System performs the corresponding inventory transactions.
    
5. System finalizes the invoice.
    
6. System reports the result to the user.
    

### Exceptions

- Invoice is already finalized.
    
- Product does not have sufficient stock.
    
- Inventory transaction fails.
    
- Invoice finalization fails.
# Exercise
## Invoice Management System

### Objective

Build an **Invoice Management System** that simulates the process of creating and issuing invoices while managing product inventory.

The goal is to provide a realistic business problem without prescribing the architecture, technologies, frameworks, or infrastructure. The solution should be designed based on the requirements and constraints identified during development.

### Business Context

The system is responsible for managing products, their available inventory, and invoices.

A product can be registered with a certain quantity available in stock. Users can then create invoices containing one or more products and their respective quantities.

An invoice starts in an **Open** state and can later be issued. Issuing an invoice represents the completion of the billing operation and must update the inventory according to the products consumed by that invoice.

The system must preserve the consistency of both the invoice and inventory throughout this process.

### Functional Requirements

#### Product Management

The system must allow users to:

- Register products;
    
- Define a unique product code;
    
- Define the product description;
    
- Define the initial available quantity;
    
- Consult registered products and their current stock.
    

#### Invoice Management

The system must allow users to create invoices containing:

- A sequential invoice number;
    
- A status;
    
- One or more products;
    
- The quantity of each product.
    

New invoices must initially have the status **Open**.

#### Invoice Issuance

Users must be able to issue an open invoice.

When an invoice is issued:

- The system must verify that the invoice can be issued;
    
- The products included in the invoice must have sufficient stock;
    
- The corresponding quantities must be deducted from inventory;
    
- The invoice must become **Closed**.
    

An invoice that has already been closed must not be issued again.

If the operation cannot be completed, the system must preserve a consistent state and provide appropriate feedback to the user.

### Important Business Scenarios

The solution should consider how the system behaves in situations such as:

#### Insufficient Inventory

A product has 5 units available, but an invoice requires 8.

What should happen to the invoice and inventory?

#### Concurrent Operations

A product has only 1 unit available and two invoices attempt to consume that unit at approximately the same time.

The system must prevent inconsistent inventory.

#### Repeated Requests

The same invoice issuance operation may be submitted more than once, for example because of a client retry or network problem.

The system should avoid consuming inventory multiple times.

#### Dependency or Processing Failure

An operation may fail after part of the process has already been executed.

The system should prevent situations such as:

- An invoice being closed without inventory being updated;
    
- Inventory being deducted while the invoice remains incorrectly open;
    
- The same inventory being consumed twice.
    
## Main Challenge

The challenge is intentionally open-ended.

Start with the **business problem**, identify its constraints and invariants, and design the solution from there.

# 11. Inventory

> **No screenshots for this chapter.** The Inventory module is switched **off** for the DoggyVille workspace, and the app sends you back to the Dashboard when you open an Inventory page. This chapter is written from the application's source code. Turn the module on in [Settings → Feature flags](14-settings.md#feature-flags) to see it, then compare against the descriptions below.

**Where (when switched on):** Inventory → Dashboard · Products · Categories · Suppliers · Purchase Orders · Movements

Inventory tracks the products you stock, where they are, and how stock changes. Set it up in this order: **Categories → Suppliers → Products → Purchase Orders**.

## Dashboard

Title: *Inventory Dashboard: Overview of your stock levels, alerts, and recent activity.* A branch selector (default *All Branches*) filters three tables:

| Table | Columns | Search | Empty message |
|-------|---------|--------|---------------|
| Low stock | Product, SKU, Current Stock, Reorder Level, Branch | *Search low stock products...* | *No low stock alerts. All products are above reorder levels.* |
| Expiry alerts | Product, Batch, Quantity, Expiry Date, Branch | *Search expiry alerts...* | *No near-expiry alerts. All batches are within safe expiry range.* |
| Recent movements | Type, Product, Quantity, Branch, Staff, Timestamp | *Search movements...* | *No recent stock movements recorded.* |

## Categories

Title: *Product Categories: Organize products into categories and subcategories.* Shown as a tree.

- **Add Category** opens a dialog with **Name** *(required, up to 100 characters, example "Dog Food")* and **Parent Category** (default *None (top-level)*).
- A category can be edited, deactivated, or deleted. A category with products linked to it cannot be deleted.

## Suppliers

Title: *Suppliers: Manage your supplier records and contact details.*

- Columns: Name, Contact Person, Email, Phone, PO Count. Search: *Search suppliers by name...*
- **Add Supplier** fields: **Name** *(required)*, **Contact Person**, **Email**, **Phone**, **Address**.
- Deleting a supplier that has purchase orders shows a warning.

## Products

Title: *Products: Manage your product catalogue, pricing, and stock tracking.*

- Columns: Name, SKU, Category, Selling Price, Status, Total Stock, Batch. Search: *Search by name or SKU...*
- Row actions: deactivate or reactivate (*Product deactivated* / *Product reactivated*), and delete. Deleting asks you to confirm, and suggests deactivating instead if the product has transaction history.
- A product's page shows its SKU and barcode, and a **Reorder Level** table per branch.

## Purchase orders

Title: *Purchase Orders: Manage purchase orders from suppliers and track stock intake.*

- Filter tabs: **All, Draft, Confirmed, Received**. Columns: Supplier, Branch, Invoice No, Total, Status, Items, Date.
- **Create** opens a three-step wizard: **1 Header** (Supplier and Branch, both required) → **2 Line Items** (Product, Quantity, Unit Cost (₹), optional Batch No and Expiry Date) → **3 Review**.
- A purchase order moves **Draft → Confirmed → Received**. Marking it **Received** adds the stock.

## Movements

Records every stock change. Columns: Type, Product, Quantity, Branch, Dest. Branch, Staff, Reason, Timestamp. Three recording dialogs:

- **Record Stock Movement:** Movement Type (*Stock In, Stock Out, Adjustment, Return*), Quantity, Branch, Reason, Reference (for example a PO number).
- **Record Stock Adjustment:** Product, Branch, Quantity (use a negative number to reduce stock, for example `-5`), and a Reason of 3 to 500 characters.
- **Record Stock Transfer:** Product, Source Branch, Destination Branch, Quantity. The destination must differ from the source.

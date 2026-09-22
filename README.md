# Smart Invoice Manager

Ek single-file invoice management app — vendors, invoices, line items, payment
status, filters, dashboard stats, aur pattern-based "AI extraction" review screen.

## Kaise chalayein

1. Is folder ko VS Code mein kholo (`File > Open Folder`).
2. `index.html` pe right-click karke **"Open with Live Server"** choose karo
   (VS Code Extensions tab se "Live Server" install karna padega agar nahi hai).
3. Ya seedha `index.html` ko double-click karke kisi bhi browser mein kholo —
   koi backend/server ki zaroorat nahi.

## Kaam kaise karta hai

- Sara data browser ke `localStorage` mein save hota hai — koi database ya
  backend setup nahi chahiye.
- Poora code `index.html` ke andar `<script>` tag mein hai (HTML + CSS + JS
  ek hi file mein — self-contained).
- Top-right ke **"Load demo data"** button se sample vendors/invoices load
  ho jaate hain demo ke liye.

## Structure (single file ke andar)

- `<style>` block — CSS variables (colors) + component classes
- `<body>` — 4 tabs: Dashboard, Invoices, Vendors, AI extraction
- `<script>` — saara JavaScript logic:
  - `loadState()` / `saveState()` — localStorage read/write
  - `addVendor()` / `renderVendors()` — vendor CRUD
  - `openInvoiceForm()` / `saveInvoiceForm()` — invoice create/edit + line items
  - `renderInvoiceList()` — search/filter
  - `renderDashboard()` — stats calculation
  - `extractInvoiceFromText()` / `runAIExtract()` — regex-based AI-style extraction

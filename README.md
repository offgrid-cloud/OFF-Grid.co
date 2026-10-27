# OFF-grid Streetwear Store (front-end prototype)

A responsive storefront and local demo owner dashboard built with HTML, CSS, and vanilla JavaScript.

## Run locally
1. Unzip the project.
2. Open `index.html` in a browser, or run a local static server from this folder (for example `python -m http.server 8000`) and visit `http://localhost:8000`.
3. Click **OWNER LOGIN** in the footer. The dashboard can be opened with **OPEN DEMO DASHBOARD WITHOUT LOGIN**.

## What's implemented
- Responsive OFF-grid storefront, product catalog and category filters
- Product details with size/color selection
- Cart, quantity controls, and Cash on Delivery checkout form
- Demo orders and product inventory saved in browser localStorage
- Owner dashboard with product add/edit/delete and order status controls
- Upload up to 20 product photos at once directly from your device (no image URLs); photos are compressed and displayed in a product gallery

## Important limitations before real launch
This is a functional visual prototype, **not a production e-commerce backend**. Product data, uploaded photos, cart, and orders are stored in the browser using localStorage. Uploaded photos are compressed to help fit browser storage limits; very large batches may need to be reduced. An order created by a customer will not appear on the owner's computer. Do not collect real customer information or rely on the demo login for security.

For production, connect a backend such as Supabase:
- Use Supabase Auth for the owner account. Create the owner user through the Supabase dashboard or a trusted server-side admin script.
- Set Row Level Security policies so public visitors can read active products and create orders through a validated server-side function, while only the authenticated owner can change products or read all orders.
- Keep service-role keys on the server only. Never embed the owner's password or privileged keys in HTML/JavaScript.
- Validate price, stock, size, quantity, and delivery fields server-side. Calculate order totals on the server, not from browser-submitted prices.
- Configure real email/order notifications and payment providers separately.

## Demo owner login
The production owner email you specified is **not wired to a real authentication service**. The demo login is deliberately not configured with your shared password. Use the demo dashboard button for preview; replace it with real authentication before publishing.

## Files
- `index.html` — storefront
- `style.css` — storefront styling
- `app.js` — products, cart, checkout demo
- `admin.html` — owner dashboard UI
- `admin.css` — dashboard styling
- `admin.js` — local demo dashboard behavior

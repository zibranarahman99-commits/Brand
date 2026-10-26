# Rahman Home — static dropshipping storefront

A mobile-friendly static storefront built with HTML, CSS and vanilla JavaScript. It includes a product catalogue, category filters, search, shopping cart, customer checkout form, WhatsApp order hand-off, and a basic UPI-app hand-off.

## Important limitations

- This is a front-end starter site, not a complete commerce backend.
- The UPI option opens a UPI app using the configured UPI ID and current item subtotal. It does **not** verify payment, create a protected order record, reconcile transactions, or automatically update inventory.
- The WhatsApp flow sends the customer’s order request to the store. The store owner must confirm stock, delivery charge, final price and payment before placing the supplier order.
- Do not advertise COD, guaranteed delivery dates, automatic refunds or verified online payments unless you have actually implemented and tested those processes.
- The sample product catalogue, descriptions and prices are placeholders. Replace them with verified supplier products and accurate prices before publishing.
- The visual product cards use a CSS fallback until you add real product image URLs.

## 1. Configure your store

Open `config.js` and change:

- `brandName`: your chosen store name. “Rahman Home” is only a provisional brand name.
- `whatsappNumber`: your WhatsApp Business number in international format, digits only. Example format: `919876543210`.
- `upiId`: your real UPI ID, such as `name@bank`. Keep blank until you are ready to accept payments.
- `upiPayeeName`: the name customers should see in their UPI app.
- `products`: replace sample products, prices, descriptions, tags and image URLs.

For each product, set `image` to a direct HTTPS image URL that you have permission to use. Do not use supplier images without checking their usage terms. Set prices only after adding product cost, fulfilment/shipping, payment costs, return/RTO reserve and any applicable tax.

Never put passwords, secret API keys, bank login details or private tokens in `config.js`. It is a public file.

## 2. Test locally

1. Extract the ZIP.
2. Open `index.html` in a modern browser, or run a local static server.
3. Test product filters, search, cart quantity, removing items, checkout validation and WhatsApp order formatting.
4. Test on a phone.
5. UPI links may only open on a device/browser with a compatible UPI app. Test with a small amount before relying on the flow.

## 3. Free hosting with GitHub Pages

1. Sign in to GitHub and create a new **public** repository, e.g. `rahman-home-store`.
2. Upload `index.html`, `styles.css`, `config.js`, `app.js`, and `README.md` to the repository root.
3. Open repository **Settings → Pages**.
4. Under build/deployment, select **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub Pages to publish the site. GitHub will show the live URL in the Pages section.
7. Open that URL on mobile and test the entire order flow.

Static hosting is free for a public GitHub repository under GitHub Pages' current standard offering, but platform policies and availability can change. A free host does not provide a backend database or payment verification automatically.

## 4. Before taking real orders

- Confirm supplier allows direct-to-customer single-order fulfilment.
- Check stock, shipping, delivery estimates, return/RTO terms and who bears costs.
- Publish accurate contact, privacy, shipping, cancellation and refund information.
- Check the GST and consumer-law requirements applicable to your actual selling setup.
- For a production-grade online payment gateway, use the gateway’s supported checkout and server-side verification/webhook flow. Never place secret gateway keys in front-end JavaScript.
- Store order records securely if you later add a backend; do not rely on a browser page as the only order record.

## Files

- `index.html` — page structure
- `styles.css` — responsive styling
- `config.js` — public store settings and sample product data
- `app.js` — catalogue, cart, checkout and order hand-off

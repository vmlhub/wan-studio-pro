# Wan Studio Pro checkout page

Standalone GitHub Pages site at `https://vmlhub.github.io/wan-studio-pro/`.
The public checkout offers PayPal and contains no payment secrets or private keys.

## Price and delivery

- The displayed price is fetched on each page load from Odoo's `/wan-paypal/checkout-config`, which reads `PAYPAL_AMOUNT_USD`.
- The PayPal button opens Odoo's checkout. Odoo sets and validates the actual order amount and emails the key after a confirmed payment.
- If the public price cannot be fetched, the page asks buyers to check the price at checkout.
- After changing `PAYPAL_AMOUNT_USD`, reload the page and verify the displayed amount and the final amount on PayPal before accepting sales.

## Publishing

The `main` branch is published through GitHub Pages from the repository root.
The Wan Studio Pro Space uses this URL for its purchase link.

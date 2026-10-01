# Wan Studio Pro checkout page

Standalone GitHub Pages site for `https://vmlhub.github.io/wan-studio-pro/`.
It contains no payment secrets or private keys.

## Publish

1. Create a **public**, empty GitHub repository named `wan-studio-pro` while signed in as `vmlhub`. Do not initialize it with a README or template.
2. From this folder, run `git push -u origin main` after the local commit is ready.
3. In the GitHub repository, open **Settings → Pages** and choose **Deploy from a branch → main → /(root)**. Save. The page URL is `https://vmlhub.github.io/wan-studio-pro/`.
4. Redeploy the latest Wise Render backend if it does not deploy automatically. Its code now allows `https://vmlhub.github.io` even when an older `ALLOWED_ORIGINS` value remains in Render.
5. Set `BUY_URL=https://vmlhub.github.io/wan-studio-pro/` in the Wan Studio Pro Hugging Face Space variables, then restart it. The app source default is also updated for its next deployment.

## Prices and delivery

- PayPal price is fetched on each page load from Odoo's `/wan-paypal/checkout-config`, which reads `PAYPAL_AMOUNT_USD`. The PayPal button opens Odoo's checkout, where the actual order amount is set and validated. If the price cannot be fetched, the page asks buyers to check it at checkout.
- Wise price is fetched from the Wise backend `/config`, where `PRICE_DISPLAY` and `PRICE_AMOUNT` must agree. Wise has its own price, which may differ from PayPal's.
- PayPal keys are emailed after a confirmed capture. Wise follows its existing separate payment process; buyers receive a reference to use with their transfer and can contact support if the key email does not arrive.
- After changing either price, reload the page and verify both the displayed amount and the final payment amount before accepting sales.

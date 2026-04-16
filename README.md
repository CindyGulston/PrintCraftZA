# PrintCraft ZA — Website

A complete 2-page website for your 3D printing store.

## Files
- `index.html` — Homepage (hero, products, how it works, testimonials)
- `customize.html` — Customizer + full checkout (design → delivery → payment → success)

---

## How to deploy (free, no coding needed)

### Option 1: Netlify Drop (EASIEST — 2 minutes)
1. Go to https://app.netlify.com/drop
2. Drag the entire `printcraft-za` folder onto the page
3. Your site goes live instantly with a free URL like `https://printcraft-za.netlify.app`
4. You can connect a custom domain like `printcraftza.co.za` in Netlify settings

### Option 2: GitHub Pages (free)
1. Create a free account at https://github.com
2. Create a new repository called `printcraft-za`
3. Upload both HTML files
4. Go to Settings → Pages → set source to main branch
5. Your site will be live at `https://yourusername.github.io/printcraft-za`

### Option 3: Shared hosting (Afrihost / Xneelo)
1. Buy a domain + hosting plan from Afrihost (https://www.afrihost.com) or Xneelo (https://xneelo.co.za)
2. Upload both files via the File Manager in cPanel
3. Done!

---

## Connect real payments (PayFast)

1. Register at https://www.payfast.co.za (free for SA merchants)
2. Get your Merchant ID and Merchant Key from your PayFast dashboard
3. Replace the `placeOrder()` function in `customize.html` with a PayFast payment form

Example PayFast integration (add inside customize.html):
```html
<form action="https://www.payfast.co.za/eng/process" method="post">
  <input type="hidden" name="merchant_id" value="YOUR_MERCHANT_ID">
  <input type="hidden" name="merchant_key" value="YOUR_MERCHANT_KEY">
  <input type="hidden" name="return_url" value="https://yoursite.com/customize.html?success=1">
  <input type="hidden" name="cancel_url" value="https://yoursite.com/customize.html">
  <input type="hidden" name="notify_url" value="https://yoursite.com/notify.php">
  <input type="hidden" name="name_first" id="pf_name">
  <input type="hidden" name="email_address" id="pf_email">
  <input type="hidden" name="amount" id="pf_amount">
  <input type="hidden" name="item_name" id="pf_item">
  <button type="submit">Pay with PayFast</button>
</form>
```

---

## Customise your store

### Change store name
Search and replace "PrintCraft ZA" in both files with your preferred name.

### Change prices
In `customize.html`, find this section and update the prices:
```javascript
const map = { keychain:[85,'Keychain'], nameplate:[120,'Name plate'], phone:[150,'Phone stand'], planter:[95,'Mini planter'] };
```

### Change colours
In both files, find `:root {` and update:
- `--purple: #6c5ce7` — main accent colour
- `--coral: #e07055` — secondary accent
- `--teal: #1d9e75` — success/confirmation colour

### Add your WhatsApp number
Search for `wa.me/27000000000` and replace `27000000000` with your number (country code + number, no spaces or +).

### Add your email
Search for `hello@printcraftza.co.za` and replace with your email.

---

## Add Google Analytics (optional)
Paste this before `</head>` in both files:
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

---

## Need help?
- PayFast docs: https://developers.payfast.co.za
- Netlify docs: https://docs.netlify.com
- The Courier Guy API: https://www.thecourierguy.co.za/api (for live shipping quotes)

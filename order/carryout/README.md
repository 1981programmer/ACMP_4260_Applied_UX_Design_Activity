# Happy Burger – Carry-Out Flow
**ACMP 4260 Applied UX Design | Group Project**
**Developer: Gregory | Branch: `gregory-branch`**

---

## My Files

I have four files spread across two folders:

```
ACMP_4260_Applied_UX_Design_Activity/
├── css/
│   └── carryout-shared.css       ← Shared styles for all three pages
└── order/
    └── carryout/
        ├── carryout-info.html    ← Step 1: Customer carry-out info form
        ├── order-review.html     ← Step 2: Order review before confirming
        ├── order-complete.html   ← Step 3: Order confirmation screen
        └── README.md             ← This file
```

No build tools, frameworks, or installs needed. These are plain HTML files
that open directly in any browser.

---

## How the Pages Connect

The three pages link to each other automatically using
`window.location.href`. Customer info and cart data are passed between
pages using the browser's `sessionStorage`.

```
[Pickup or Delivery page – teammate's work]
             ↓  (saves cart to sessionStorage, links here)
    carryout-info.html       ← Step 1
             ↓
    order-review.html        ← Step 2
             ↓
    order-complete.html      ← Step 3
             ↓
       index.html            ← Home page
```

---

## How to Integrate With My Pages

### Passing the cart from the ingredient-selection page

Whoever built the ingredient-selection page needs to do one thing before
linking to my pages: save the cart array to `sessionStorage` like this:

```js
// Run this on the ingredient-selection or pickup/delivery page
// before navigating to carryout-info.html

const cart = [
  { name: "Classic Smash Burger", cost: 9.99 },
  { name: "Crispy Fries (lg)",    cost: 3.49 },
  // ...add all selected items here
];

sessionStorage.setItem('cart', JSON.stringify(cart));
window.location.href = 'order/carryout/carryout-info.html';
```

That's all they need to do. My pages will pick up the cart data
automatically and display the correct items and totals.

### Linking back to the home page

The "Return to Home" button on `order-complete.html` currently points to:
```
../../index.html
```
This assumes `index.html` is at the project root, which it should be.
If the home page has a different name or location, just update that one
line in `order-complete.html`.

---

## GitHub Workflow

```bash
# 1. Make sure you are on your branch
git checkout gregory-branch

# 2. Pull the latest from main so you are up to date
git pull origin main

# 3. Stage your files
git add css/carryout-shared.css
git add order/carryout/

# 4. Commit with a clear message
git commit -m "feat: add carry-out info, review, and confirmation pages"

# 5. Push to your branch
git push origin gregory-branch

# 6. Open a Pull Request on GitHub to merge into main
#    https://github.com/1981programmer/ACMP_4260_Applied_UX_Design_Activity
```

---

## No Extra Setup Needed

These are plain `.html` files. To test them locally just open
`carryout-info.html` in your browser — no installs, no terminal commands,
no build steps required.

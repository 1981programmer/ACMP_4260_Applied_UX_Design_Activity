# 🍔 Happy Burger
**ACMP 4260 Applied UX Design | Group Project**

Happy Burger is a high-fidelity interactive prototype for a restaurant website
where customers can order customizable burgers for carry-out or delivery.

---

## 👥 Team Members & Responsibilities

| Name | Branch | Pages |
|---|---|---|
| Gregory Treihart | `gregory-branch` | Carry-Out Info, Carry-Out Order Review, Carry-Out Order Complete |
| Allan Hernandez | *(ask Allan)* | Delivery Address, Delivery Order Review, Delivery Order Complete |
| Hennysa Omoregie | `henny` | Home Page, Menu Page |
| Laurelle Sekpe | *(ask Laurelle)* | Order Online Page, Choose Ingredients Page |

---

## 📁 Project Structure

```
ACMP_4260_Applied_UX_Design_Activity/
├── index.html              ← Home page
├── css/
│   └── carryout-shared.css ← Shared styles for carry-out pages
├── images/                 ← All images and icons used on the site
├── js/                     ← Any shared JavaScript files
├── menu/                   ← Menu page
├── order/
│   ├── carryout/           ← Gregory's pages
│   │   ├── carryout-info.html
│   │   ├── order-review.html
│   │   ├── order-complete.html
│   │   └── README.md
│   └── delivery/           ← Allan's pages
└── shop/                   ← Shop page
```

---

## 🌐 Website Flow

```
Home Page
├── Shop
├── Menu
└── Order Online
         ↓
   Choose Ingredients
         ↓
   Pickup or Delivery?
    ↙               ↘
Carry-Out         Delivery
  Info             Address
    ↓                 ↓
 Review            Review
    ↓                 ↓
Complete          Complete
```

---

## 🛠️ Technology

This project is built with plain **HTML, CSS, and JavaScript** — no frameworks
or build tools are needed. Every page opens directly in a browser.

Data is passed between pages using the browser's `sessionStorage`. The most
important piece of shared data is the **cart**, which is an array of items
shaped like this:

```js
[
  { name: "Classic Smash Burger", cost: 9.99 },
  { name: "Crispy Fries (lg)",    cost: 3.49 },
]
```

Whoever builds the Choose Ingredients page needs to save the cart to
`sessionStorage` before linking to either the carry-out or delivery pages:

```js
sessionStorage.setItem('cart', JSON.stringify(cart));
```

---

## 🔀 GitHub Workflow

Everyone on the team should follow these steps. **Do not push directly to
`main`** — always work on your own branch and open a Pull Request.

```bash
# 1. Clone the repository (only needed once)
git clone https://github.com/1981programmer/ACMP_4260_Applied_UX_Design_Activity.git

# 2. Switch to your branch (create it if it does not exist yet)
git checkout -b your-branch-name

# 3. Pull the latest from main before starting any new work session
git pull origin main

# 4. Do your work, then stage your files
git add .

# 5. Commit with a clear, descriptive message
git commit -m "feat: describe what you added or changed"

# 6. Push to your branch
git push origin your-branch-name

# 7. Go to GitHub and open a Pull Request to merge into main
#    https://github.com/1981programmer/ACMP_4260_Applied_UX_Design_Activity
```

### ⚠️ Important Git Rules
- Always run `git pull origin main` before starting a new work session so you have everyone's latest changes.
- Never push directly to `main`.
- Write clear commit messages so teammates know what changed.
- If you are unsure about a merge conflict, message Gregory on Discord before resolving it since he is managing the repository.

---

## 🔗 Connecting Pages Across Teammates

### Henny & Laurelle → Gregory and Allan
The Choose Ingredients page needs to save the cart to `sessionStorage` and
then link to the Pickup or Delivery decision. From there the link should
point to either:
- `order/carryout/carryout-info.html` for carry-out (Gregory's page)
- `order/delivery/` for delivery — confirm the exact filename with Allan

### Gregory → Henny & Laurelle
The "Return to Home" button on `order-complete.html` links to
`../../index.html`. Please make sure the home page is saved as `index.html`
at the project root.

### Allan → Henny & Laurelle
Same situation — confirm with Allan what filename his final confirmation
page links back to so Henny and Laurelle can make sure it matches.

---

## ✅ Progress Tracker

Update this table as pages get completed and merged into main.

| Page | Owner | Status |
|---|---|---|
| Home Page | Henny | ✅ Complete |
| Menu Page | Henny | ⬜ Not started |
| Order Online | Laurelle | ⬜ Not started |
| Choose Ingredients | Laurelle | ⬜ Not started |
| Carry-Out Info | Gregory | ✅ Complete |
| Carry-Out Order Review | Gregory | ✅ Complete |
| Carry-Out Order Complete | Gregory | ✅ Complete |
| Delivery Address | Allan | ⬜ Not started |
| Delivery Order Review | Allan | ⬜ Not started |
| Delivery Order Complete | Allan | ⬜ Not started |

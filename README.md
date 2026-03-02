# 🍔 Happy Burger
**ACMP 4260 Applied UX Design | Group Project**

Happy Burger is a high-fidelity interactive prototype for a restaurant website
where customers can order customizable burgers for carry-out or delivery.

---

## 👥 Team Members & Responsibilities

| Name | Branch | Pages |
|---|---|---|
| Gregory Treihart | `gregory-branch` | Carry-Out Info, Carry-Out Order Review, Carry-Out Order Complete |
| Allan Hernandez | `Delivery-and-Checkout` | Delivery Address, Delivery Order Review, Delivery Order Complete |
| Hennysa Omoregie | `henny` | Home Page, Menu Page |
| Laurelle Sekpe | `laurelle-branch` | Order Online Page, Choose Ingredients Page |

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

This project is built with plain **HTML, CSS, and JavaScript**. Every page opens directly in a browser.

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
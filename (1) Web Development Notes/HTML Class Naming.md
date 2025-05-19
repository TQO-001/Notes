# 🧠 HTML Class Naming Cheat Sheet for Web Developers

## 📚 Table of Contents
- [General Conventions](#-general-conventions)
- [1. Common Layout Structures](#1-common-layout-structures)
- [2. Component Blocks](#2-component-blocks)
- [3. Text & Typography](#3-text--typography)
- [4. Utilities (Non-Tailwind)](#4-utilities-non-tailwind)
- [5. State & Behavior](#5-state--behavior)
- [6. User & Profile Related](#6-user--profile-related)
- [7. E-Commerce / Product Naming](#7-e-commerce--product-naming)
- [8. Dashboard / App UI](#8-dashboard--app-ui)
- [9. Blog / CMS / Article Layouts](#9-blog--cms--article-layouts)
- [10. Media & Galleries](#10-media--galleries)
- [11. Responsive Helpers](#11-responsive-helpers)
- [12. Custom Interactive Elements](#12-custom-interactive-elements)
- [13. Navigation & Breadcrumbs](#13-navigation--breadcrumbs)
- [14. Forms & Inputs](#14-forms--inputs)
- [15. Naming Tips (Quick Rules)](#15-naming-tips-quick-rules)

---

## ✅ General Conventions
Basic rules for writing clean, readable, and scalable class names using semantic structure, BEM syntax, and consistent naming patterns.
- Use `kebab-case`
- Prioritize semantic over visual names
- Use BEM (`block__element--modifier`)
- Prefix contextually to avoid class collisions
- State and modifier prefixes: `is-`, `has-`, `--mod`
---

## 1. Common Layout Structures
Names for structural layout containers like grids, wrappers, and columns that organize the general flow of the page.

```

.container  
.wrapper  
.section  
.row  
.col  
.grid  
.stack  
.centered  
.main  
.sidebar  
.footer  
.header

```

---

## 2. Component Blocks
Reusable interface elements like navbars, buttons, cards, and modals using BEM (`block__element--modifier`) naming structure.

```

.navbar  
.navbar__item  
.navbar__toggle

.hero  
.hero__title  
.hero__subtitle

.card  
.card__header  
.card__body  
.card__footer

.button or .btn  
.btn--primary  
.btn--secondary  
.btn--icon  
.btn--loading

.form  
.form__group  
.form__label  
.form__input  
.form__error

.modal  
.modal__header  
.modal__body  
.modal__footer  
.modal--open

.toast  
.toast--success  
.toast--error

.badge  
.badge--new  
.badge--warning

.dropdown  
.dropdown__menu  
.dropdown__item  
.dropdown--open

```

---

## 3. Text & Typography
Class names for styling text content like headings, captions, emphasis, and alignment.

```

.title  
.subtitle  
.text  
.text-muted  
.text-center  
.text-right  
.text-left  
.lead  
.caption

```

---

## 4. Utilities (Non-Tailwind)
Small helper classes for margins, padding, display, alignment, shadows, and colors — useful when not using utility-first CSS like Tailwind.

```

.p-1, .p-2, .p-4  
.m-1, .m-2, .m-4  
.text-bold  
.text-italic  
.bg-white, .bg-dark, .bg-primary  
.text-white, .text-dark  
.hidden  
.d-block, .d-inline  
.flex, .flex-row, .flex-col  
.items-center, .justify-between  
.rounded, .rounded-sm, .rounded-lg  
.shadow, .shadow-sm, .shadow-lg

```

---

## 5. State & Behavior
Descriptive flags for dynamic states or conditions of UI components such as visibility, activity, or form validation.

```

.is-active  
.is-disabled  
.is-loading  
.is-visible  
.is-hidden  
.is-open  
.is-closed  
.has-error  
.has-success

```

---

## 6. User & Profile Related
Classes specific to user-centric UI components like avatars, bios, stats, and profiles.

```

.user-card  
.user-avatar  
.user-name  
.user-bio  
.profile-header  
.profile__stats

```

---

## 7. E-Commerce / Product Naming
Use these for typical store, cart, product listing, and checkout elements in an e-commerce website.

```

.product  
.product__image  
.product__title  
.product__price  
.product__description  
.product--sale  
.cart  
.cart__item  
.cart__total  
.checkout-form

```

---

## 8. Dashboard / App UI
Class names used in SaaS dashboards, admin panels, or internal tools with widgets, panels, and data displays.

```

.sidebar  
.sidebar__item  
.dashboard  
.dashboard__stat  
.panel  
.panel__header  
.panel__body  
.widget  
.widget__title  
.widget--warning

```

---

## 9. Blog / CMS / Article Layouts
Used in content-heavy platforms like blogs or CMS where articles, posts, metadata, and sidebars are common.

```

.article  
.article__header  
.article__content  
.article__author  
.post  
.post__meta  
.blog-sidebar  
.read-more

```

---

## 10. Media & Galleries
Classes for displaying image or video galleries, media cards, and other visual content layouts.

```

.gallery  
.gallery__item  
.gallery__image  
.video-wrapper  
.media  
.media__thumb  
.media__content

```

---

## 11. Responsive Helpers
Class names for controlling visibility or layout across screen sizes; especially useful with custom breakpoints.

```

.mobile-only  
.desktop-only  
.tablet-hidden  
.sm:flex  
.md:block  
.lg:grid

```

---

## 12. Custom Interactive Elements
Used for accordions, tabs, sliders, and other JavaScript-enhanced components that require expanded/collapsed or active states.

```

.accordion  
.accordion__item  
.accordion__header  
.accordion__body  
.accordion--open

.tab  
.tab__list  
.tab__item  
.tab__content  
.tab--active

```

---

## 13. Navigation & Breadcrumbs
Common navigation-related structures like links, pagination, breadcrumbs, and menus.

```

.breadcrumb  
.breadcrumb__item  
.breadcrumb__link  
.pagination  
.pagination__item  
.pagination__next

```

---

## 14. Forms & Inputs
Form field naming, including groupings, states, icons, and types of inputs (checkbox, select, etc.).

```

.input  
.input--error  
.input--disabled  
.input-group  
.input-label  
.input-icon  
.checkbox  
.radio  
.switch  
.select

```

---

## 15. Naming Tips (Quick Rules)

| Use Case         | Naming Rule                          |
|------------------|--------------------------------------|
| Container        | `something-container`, `wrapper`     |
| Block Component  | `.component`, `.component__child`    |
| Modifier         | `--variant`, `--highlighted`         |
| State            | `is-`, `has-`                        |
| Action Button    | `btn`, `btn--action`, `btn--small`   |
| Layout Section   | `section`, `hero`, `footer`          |
| Utility Class    | Keep short & functional (`.p-4`, `.d-flex`) |

---

```

Would you like this in a downloadable `.md` file now? I can generate it for you instantly.
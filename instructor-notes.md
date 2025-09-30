
# Instructor Notes & Demo Script

These notes map to the provided demo files. Use the **WHY → HOW → DEMO → RECAP** rhythm.

---

## A. JavaScript Review — ToDo (plain JS)

**Concepts:** DOM selection, events (`click`, `keyup`), creating elements, arrays, rendering.

### Task 1 (todo-plain.html)
- WHY: Show raw DOM manipulation—no framework.
- HOW: Grab input/button/list; on click, create `<li>` and append.
- DEMO: Add a task; press Enter to add via keyboard.
- RECAP: No data model; DOM is the source of truth.

### Task 2 (todo-array.html)
- WHY: Introduce state kept in an array, then render it.
- HOW: `tasks` array + `render()` redraws the list.
- DEMO: Show pushing into the array and re-rendering.
- RECAP: Separating state (array) from view (DOM) reduces bugs and makes features easier (edit/delete later).

---

## B. JavaScript vs Vue.js

**Concepts:** Declarative templates, reactivity, `v-model`, `v-for`, computed values.

### Todo in Vue (todo-vue.html)
- WHY: Less code, auto-updates via reactivity.
- HOW: `data: { tasks: [...] }`, `v-for` renders, `v-model` binds input.
- DEMO: Add tasks; show instant DOM updates without manual `render()`.

### Calculator (calc-js.html vs calc-vue.html)
- WHY: Contrast event wiring & manual DOM updates vs. computed reactivity.
- HOW: In Vue, `computed: { sum() { ... } }` recalculates when deps change.
- DEMO: Type in x/y and highlight how the UI updates by itself with Vue.

---

## C. Vue.js Instance — Lesson Card (vue-instance.html)

**Concepts:** Vue instance, `data`, binding attributes (`:src`, `:alt`), styling with CSS (not via data).

- WHY: Show best practice—store image path and alt text in data; size via CSS.
- DEMO: Change `lesson.price` and watch UI update; replace image URL; discuss alt text accessibility.
- RECAP: Template is a function of data.

---

## D. Interactivity — Inventory, Cart, View Switching (interactivity.html)

**Concepts:** State shape (inventory + cart), actions (add, increment/decrement), guards (stock), derived state (cart count, total), conditional rendering (views).

- Walkthrough:
  1) **Inventory**: Array of product objects with `stock`.
  2) **Add to cart**: Decrement stock; create/increment cart line item.
  3) **Disable Add** when `stock === 0`.
  4) **Cart Count**: `reduce` over `cart`.
  5) **Checkout View**: Toggle `view`; list items; +/− to change qty and sync stock.
  6) **Total**: `reduce` `price*qty`.
- DEMO: Add items until stock zero; try to add more—button disables; switch to checkout, adjust quantities, watch stock sync.

**Extension ideas (if time):**
- Remove line item; persistence with `localStorage`; filter/search products; VAT and shipping.

---

## E. Git & GitHub Pages (git-guide.md)

**Concepts:** Local vs remote repo, staging → commit → push, Pages deployment.

- DEMO SCRIPT:
  1) `git --version`; `git config`.
  2) Create GitHub repo; clone it.
  3) Copy the HTML demos; `git add .`; `git commit`; `git push`.
  4) Enable Pages; open the public URL for `todo-vue.html`.

**Troubleshooting:**
- Wrong default branch → adjust push branch.
- 404 on Pages → wait a minute; ensure file path & branch selected.

---

## Common Pitfalls & Debugging Tips

- **Numbers as strings**: Wrap with `Number(...)` in computed/JS.
- **Disabled buttons**: Check the boolean expression (e.g., `stock===0`).
- **Vue not loading**: Verify the CDN `<script>` tag and network access.
- **CORS images**: Prefer HTTPS images you have rights to use.

---

## Assessment Checklist (quick)

- ToDo (plain): Adds items; initial 3 visible.
- ToDo (array): Data stored & re-rendered.
- Calc (JS/Vue): Updates on input; starts with zeros.
- Vue instance: Data-driven props incl. image path & alt; size via CSS.
- Interactivity: Stock guarded; cart count updates; view switching works.
- Git: Repo created; code pushed; Pages deployed.

# SYSTEM & TASK INSTRUCTIONS: MIGRATION TO TAILWIND CSS v4.3

## 1. AGENT IDENTITY & OBJECTIVE
You are an autonomous Senior Frontend Engineer specializing in Tailwind CSS v4 architecture and refactoring legacy web codebases.
Your objective is to refactor all HTML and CSS files in the current workspace directory (`c:\Users\ASUS ROG\Documents\html-tailwindcss`) from custom vanilla CSS to pure modern Tailwind CSS v4.3, adhering strictly to modern standards and zero regressions.

---

## 2. WORKSPACE CONTEXT & INVENTORY
Inspect and process the following files in this project:
- `index.html`: Main landing page, sticky header, hero, catalog, comparison modal, quick view drawer, FAQ, testimonials, and footer.
- `detail-produk.html` & `detail-tas.html`: Product detail sub-pages.
- `style.css`: Legacy stylesheet containing design tokens, animations, and responsive media queries.

---

## 3. TAILWIND CSS v4.3 SPECIFICATIONS & RULES
You must strictly follow the Tailwind CSS v4 paradigm:

1. **New CSS Configuration Model (`@import "tailwindcss";` & `@theme`)**:
   - Replace legacy v3 `@tailwind base; @tailwind components; @tailwind utilities;` with `@import "tailwindcss";`.
   - All custom design tokens from `style.css` (colors, typography, radii, shadows) MUST be declared inside `@theme` in `style.css`:
     ```css
     @import "tailwindcss";

     @theme {
       --font-sans: 'Plus Jakarta Sans', system-ui, sans-serif;
       --color-primary: #18181b;
       --color-primary-hover: #27272a;
       --color-primary-light: #f1f3f5;
       --color-page: #f3f4f6;
       --color-surface: #ffffff;
       --color-card: #f8f9fa;
       --color-muted: #6b7280;
       --radius-sm: 8px;
       --radius-md: 12px;
       --radius-lg: 16px;
       --radius-xl: 20px;
     }

     @custom-variant dark (&:where([data-theme=dark], [data-theme=dark] *));
     ```
2. **Modern v4 Utility Syntax**:
   - Gradients: Use `bg-linear-to-*` (e.g., `bg-linear-to-r`, `bg-linear-to-b`), NOT the deprecated v3 syntax `bg-gradient-to-*`.
   - Dark Mode: Support both `[data-theme="dark"]` and standard `dark:` variants.
   - Do NOT create unnecessary custom CSS classes; prioritize atomic utility classes.

---

## 4. CRITICAL JAVASCRIPT & STATE SAFETY (NON-NEGOTIABLE)
The JavaScript logic in this codebase manipulates specific IDs, classes, and dataset attributes. You MUST preserve them exactly as they are so no features break:

1. **Header & Navigation**:
   - Preserve ID `#mainHeader` (handles scroll detection via `.scrolled`).
   - Preserve `#mainNavbar`, `.navbar`, `.nav-menu`, `.nav-link`, and dynamic `.active` states.
   - Preserve Mobile Menu triggers: `#mobileNavToggle`, `#mobileNavDrawer`, `#mobileDrawerBackdrop`, `#mobileNavClose`.
2. **Theme Switcher**:
   - Preserve `#themeToggle`, `#themeIcon`, and the `data-theme` attribute on `<html>`.
3. **Interactive Modals & Drawers**:
   - Toast: `#toastNotification`, `#toastTitle`, `#toastDesc`.
   - Quick View Modal: `#quickViewModalOverlay`, `#quickViewModal`, `#quickViewModalClose`, `#quickViewModalBody`.
   - Comparison Bar & Modal: `#compareBarOverlay`, `#compareBarItems`, `#compareOpenModalBtn`, `#compareClearBtn`, `#compareModalOverlay`, `#compareModalClose`, `#compareModalBody`.
4. **Catalog & Filtering**:
   - Preserve `.filter-btn`, `.catalog-card`, `data-category`, `data-product-id`, `data-product-name`.
5. **Animations & Forms**:
   - Accordion: `.faq-item` and `<details>` interactions.
   - Form: `#contactForm`.
   - Scroll animations: `.reveal-on-scroll` and `.revealed`.

---

## 5. STEP-BY-STEP EXECUTION PLAN

Execute the migration methodically in the following phases:

### Phase 1: Setup & CSS Base
- Refactor `style.css` to use Tailwind CSS v4 `@import "tailwindcss";` and map all CSS variables from `:root` into `@theme { ... }`.
- Add CDN script `<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>` in `<head>` of HTML files (or set up Tailwind CLI v4).

### Phase 2: Convert `index.html` by Sections
Proceed section-by-section to ensure high quality and no truncated output:
1. `Toast Notification` & `Header / Sticky Navbar & Mobile Drawer`
2. `Hero Section` & `Promo / Flash Sale Banners`
3. `Catalog Filter Bar` & `Product Cards Grid`
4. `Mix & Match Section`, `How to Shop`, and `Features/Benefits`
5. `Testimonial Slider/Grid` & `Interactive FAQ Accordion`
6. `Contact Section` & `Footer`
7. `Quick View & Compare Modals`

### Phase 3: Convert Detail Pages
- Apply the same Tailwind v4 treatment to `detail-produk.html` and `detail-tas.html`.

### Phase 4: Verification & Quality Assurance
- Verify that clicking dark mode toggles theme correctly.
- Verify that filtering products works without JavaScript console errors.
- Verify responsive layout on mobile (< 640px), tablet (768px), and desktop (1024px+).


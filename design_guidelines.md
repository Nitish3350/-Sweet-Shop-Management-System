# Sweet Shop Management System - Design Guidelines

## Design Approach

**Reference-Based E-commerce Design** drawing inspiration from Shopify and Etsy's product-centric layouts, combined with Linear's clean typography and modern SaaS dashboard patterns for the admin interface.

**Core Principle**: Create a delightful, appetizing experience that makes sweets irresistible while maintaining professional inventory management tools.

---

## Typography System

**Font Stack**: 
- Primary: 'Plus Jakarta Sans' (Google Fonts) - headings, buttons, navigation
- Secondary: 'Inter' (Google Fonts) - body text, forms, data tables

**Hierarchy**:
- Hero Headline: text-5xl md:text-7xl, font-bold
- Section Headers: text-3xl md:text-4xl, font-bold
- Product Names: text-xl md:text-2xl, font-semibold
- Body Text: text-base, font-normal
- Small Text/Labels: text-sm, font-medium

---

## Layout & Spacing

**Spacing Primitives**: Use Tailwind units of 4, 6, 8, 12, and 16 consistently.
- Component padding: p-6 to p-8
- Section spacing: py-12 md:py-16 lg:py-20
- Card gaps: gap-6 to gap-8
- Element margins: mb-4, mb-6, mb-8

**Container Strategy**:
- Full-width hero: w-full with max-w-7xl inner container
- Content sections: max-w-6xl mx-auto
- Admin dashboard: max-w-screen-2xl

---

## Page Structures

### Public Sweet Shop (Landing/Browse)

**Hero Section** (h-[600px] md:h-[700px]):
- Full-width hero image showing colorful assorted sweets display
- Centered content with blurred-background overlay for text/CTA
- Primary CTA: "Browse Our Sweets" with backdrop-blur-md bg-white/20 treatment
- Secondary login link positioned top-right

**Sweet Grid Section**:
- Masonry-style product grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4
- Each sweet card includes: high-quality product image, name, category badge, price, stock indicator, purchase button
- Floating search/filter bar with category pills and price range slider
- Cards with subtle elevation (shadow-lg) and rounded-2xl borders

**Search & Filter Panel**:
- Sticky sidebar (hidden on mobile, drawer on tablet)
- Category checkboxes with sweet type icons (Heroicons)
- Price range dual slider
- "In Stock Only" toggle

### Authentication Pages

**Login/Register**:
- Split-screen layout on desktop (50/50)
- Left: Form on minimal background (max-w-md)
- Right: Full-bleed appetizing sweet shop imagery
- Mobile: Single column, image header (h-48)
- Social auth buttons if using Replit Auth

### Admin Dashboard

**Layout**: Sidebar + main content area
- Left sidebar (w-64): Navigation with icons (Heroicons), user profile, logout
- Main content: Full-width data tables and forms
- Dashboard cards showing: Total Sweets, Low Stock Alerts, Recent Purchases (grid-cols-1 md:grid-cols-3)

**Inventory Table**:
- Sortable columns: ID, Image thumbnail, Name, Category, Price, Stock, Actions
- Row actions: Edit (pencil icon), Delete (trash icon), Restock (plus icon)
- Inline stock badges (red for <10, yellow for <30, green for 30+)

**Add/Edit Sweet Form**:
- Two-column layout on desktop: left for form fields, right for image preview
- Fields: Name, Category (dropdown), Price (number input with currency symbol), Stock Quantity, Description (textarea)
- Image upload with drag-and-drop zone
- Action buttons: Save (primary), Cancel (secondary)

---

## Component Library

### Cards
- Sweet Product Card: rounded-2xl, overflow-hidden, shadow-lg hover:shadow-xl transition
- Stat Dashboard Card: rounded-xl, p-6, with large number display and trend indicator

### Buttons
- Primary: px-6 py-3, rounded-lg, font-semibold, transition-all
- Secondary: Same sizing, with border treatment
- Icon buttons: w-10 h-10, rounded-full for table actions
- Disabled state: opacity-50, cursor-not-allowed

### Forms
- Input fields: px-4 py-3, rounded-lg, border treatment, focus ring
- Labels: text-sm, font-medium, mb-2
- Error messages: text-sm with alert icon

### Navigation
- Top nav (public): Transparent on hero, solid on scroll, flex justify-between items-center, h-16
- Admin sidebar: Fixed left, full-height, with icon-text navigation items

### Badges & Pills
- Category badges: px-3 py-1, rounded-full, text-xs, font-medium
- Stock indicators: Small circle or pill with quantity

### Icons
Use **Heroicons** (outline for navigation, solid for actions):
- Shopping cart, heart (wishlist), search, filter, user, logout, pencil, trash, plus, minus, chart-bar

---

## Images

**Required Images**:
1. **Hero Background**: Large, high-quality image of colorful assorted sweets in glass jars or display case (full-bleed, h-[600px] md:h-[700px])
2. **Sweet Product Images**: Square format (400x400px minimum), showing individual sweets on clean backgrounds
3. **Auth Page Side Image**: Atmospheric sweet shop interior or candy display close-up
4. **Empty State Illustrations**: Placeholder for "No sweets found" search results

**Image Treatment**:
- Product images: rounded-xl, object-cover
- Hero: object-cover object-center with overlay gradient
- Buttons over images: backdrop-blur-md with bg-white/20 or bg-black/30

---

## Responsive Behavior

- Mobile (base): Single column, stacked navigation (hamburger menu), full-width cards
- Tablet (md:): 2-column grids, sticky filter sidebar becomes drawer
- Desktop (lg:): 3-4 column grids, persistent sidebar, expanded forms

---

## Animation Guidelines

**Minimal, purposeful animations only**:
- Card hover: Scale up slightly (scale-105) with shadow increase
- Button interactions: Built-in transitions
- Page transitions: Simple fade-in for content
- NO scroll-triggered animations, parallax, or complex effects

---

This design creates an inviting, professional sweet shop experience that balances delightful product browsing with efficient admin management tools.
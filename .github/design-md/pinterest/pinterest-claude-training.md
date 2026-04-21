# Claude Training: Pinterest Design System Implementation

## Training Objective
Train Claude to accurately implement Pinterest's warm, inspiration-driven design system characterized by photography-first layouts, warm neutral palettes, and generous rounded corners.

## Core Design Philosophy

Pinterest differs from typical tech platforms through:
- **Warmth over sterility**: Olive/sand-toned neutrals instead of cool grays
- **Singular bold accent**: Pinterest Red (#e60023) as the only vibrant color
- **Photography dominance**: Content (pins/images) creates visual interest, not shadows or decoration
- **Generous rounding**: 16px+ border-radius on most elements
- **Compact typography**: Dense information hierarchy with 12-16px functional text

## Critical Color Rules

### What to Use
```css
/* Primary Brand */
--pinterest-red: #e60023;        /* CTAs only - bold and singular */

/* Text Hierarchy */
--plum-black: #211922;           /* Primary text - warm undertone */
--olive-gray: #62625b;           /* Secondary text */
--warm-silver: #91918c;          /* Disabled states, borders */

/* Surfaces */
--sand-gray: #e5e5e0;            /* Secondary buttons - warm, craft-like */
--warm-light: #e0e0d9;           /* Circular buttons, badges */
--warm-wash: hsla(60,20%,98%,.5); /* Subtle warm overlay */

/* Interactive */
--focus-blue: #435ee5;           /* Focus rings */
--link-blue: #2b48d4;            /* Links */
```

### What NOT to Use
- ❌ Cool grays (#ccc, #999, #666) - always use warm equivalents
- ❌ Pure black (#000) as primary text - use plum black (#211922)
- ❌ Multiple brand colors - Pinterest Red is singular
- ❌ Harsh shadows - Pinterest relies on content depth

## Typography Implementation

### Font Stack
```css
font-family: Pin Sans, -apple-system, system-ui, Segoe UI, Roboto, 
             Oxygen-Sans, Apple Color Emoji, Segoe UI Emoji, 
             Segoe UI Symbol, Ubuntu, Cantarell, Fira Sans, 
             Droid Sans, Helvetica Neue, Helvetica, 
             ヒラギノ角ゴ Pro W3, メイリオ, Meiryo, 
             ＭＳ Ｐゴシック, Arial, sans-serif;
```

### Type Scale
```css
/* Display - Maximum impact */
.hero-heading {
  font-size: 70px;
  font-weight: 600;
  color: #211922;
}

/* Section Headings */
.section-title {
  font-size: 28px;
  font-weight: 700;
  letter-spacing: -1.2px; /* Negative tracking for coziness */
  color: #211922;
}

/* Body Text */
.body {
  font-size: 16px;
  font-weight: 400;
  line-height: 1.4;
  color: #211922;
}

/* UI Elements */
.button, .caption {
  font-size: 12px;
  font-weight: 400-500;
  line-height: 1.5;
}
```

## Component Patterns

### Primary Button
```css
.btn-primary {
  background: #e60023;
  color: #000;                    /* Black text on red - unusual but correct */
  padding: 6px 14px;
  border-radius: 16px;            /* Rounded, NOT pill-shaped */
  border: 2px solid transparent;
  font-size: 12px;
  font-weight: 400;
}

.btn-primary:focus {
  outline: 2px solid #435ee5;
  outline-offset: 2px;
}
```

### Secondary Button
```css
.btn-secondary {
  background: #e5e5e0;            /* Warm sand - the signature Pinterest look */
  color: #000;
  padding: 6px 14px;
  border-radius: 16px;
  font-size: 12px;
}
```

### Circular Action Button
```css
.btn-circular {
  background: #e0e0d9;
  color: #211922;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Input Field
```css
.input {
  background: #ffffff;
  border: 1px solid #91918c;
  border-radius: 16px;
  padding: 11px 15px;
  font-size: 16px;
  color: #211922;
}

.input:focus {
  outline: 2px solid #435ee5;
  outline-offset: 1px;
}
```

### Pin Card
```css
.pin-card {
  background: #ffffff;
  border-radius: 16px;
  overflow: hidden;
  /* NO box-shadow - Pinterest is flat */
}

.pin-card img {
  width: 100%;
  height: auto;
  display: block;
}

.pin-card-description {
  padding: 12px;
  font-size: 16px;
  color: #62625b;              /* Olive gray for metadata */
}
```

## Border-Radius Scale

```css
--radius-standard: 12px;         /* Small cards, links */
--radius-button: 16px;           /* Buttons, inputs, medium cards */
--radius-comfortable: 20px;      /* Feature cards */
--radius-large: 28px;            /* Large containers */
--radius-section: 32px;          /* Tab elements, panels */
--radius-hero: 40px;             /* Hero containers */
--radius-circle: 50%;            /* Action buttons */
```

**Rule**: Never use border-radius less than 12px on cards. The generous rounding is core to Pinterest's identity.

## Layout Principles

### Spacing System
```css
/* Base unit: 8px */
--space-xs: 4px;
--space-sm: 8px;
--space-md: 16px;
--space-lg: 24px;
--space-xl: 32px;
--space-2xl: 80px;
--space-3xl: 100px;
```

### Masonry Grid (Signature Layout)
```css
.pin-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(236px, 1fr));
  gap: 16px;
  /* Content density IS the value - pack pins tightly */
}
```

### Responsive Breakpoints
```css
/* Mobile */
@media (max-width: 576px) {
  .pin-grid { grid-template-columns: 1fr; }
}

/* Tablet */
@media (min-width: 768px) {
  .pin-grid { grid-template-columns: repeat(auto-fill, minmax(236px, 1fr)); }
}

/* Desktop */
@media (min-width: 1312px) {
  .pin-grid { grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); }
}
```

## Training Prompts & Examples

### Example 1: Hero Section
**Prompt**: "Create a Pinterest-style hero section"

**Correct Implementation**:
```html
<section class="hero" style="background: #ffffff; padding: 80px 24px;">
  <h1 style="
    font-size: 70px; 
    font-weight: 600; 
    color: #211922;
    text-align: center;
    margin-bottom: 24px;">
    Find your next idea
  </h1>
  <div style="display: flex; gap: 12px; justify-content: center;">
    <button style="
      background: #e60023; 
      color: #000; 
      padding: 6px 14px; 
      border-radius: 16px;
      border: none;
      font-size: 12px;">
      Get started
    </button>
    <button style="
      background: #e5e5e0; 
      color: #000; 
      padding: 6px 14px; 
      border-radius: 16px;
      border: none;
      font-size: 12px;">
      Learn more
    </button>
  </div>
</section>
```

### Example 2: Pin Grid
**Prompt**: "Create a masonry pin grid"

**Correct Implementation**:
```html
<div style="
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(236px, 1fr));
  gap: 16px;
  padding: 24px;">
  
  <div style="
    background: #ffffff;
    border-radius: 16px;
    overflow: hidden;">
    <img src="pin-image.jpg" style="width: 100%; display: block;">
    <div style="padding: 12px;">
      <p style="font-size: 16px; color: #62625b; margin: 0;">
        Pin description
      </p>
    </div>
  </div>
  
  <!-- Repeat for more pins -->
</div>
```

### Example 3: Search Bar
**Prompt**: "Create Pinterest's signature search bar"

**Correct Implementation**:
```html
<div style="
  background: #ffffff;
  border: 1px solid #91918c;
  border-radius: 16px;
  padding: 11px 15px;
  display: flex;
  align-items: center;
  gap: 8px;">
  <svg width="16" height="16" style="color: #91918c;">
    <!-- Search icon -->
  </svg>
  <input 
    type="text" 
    placeholder="Search for ideas"
    style="
      border: none;
      outline: none;
      flex: 1;
      font-size: 16px;
      color: #211922;
      background: transparent;">
</div>
```

## Common Mistakes to Avoid

### ❌ Incorrect
```css
/* Using cool grays */
background: #e0e0e0;  /* Too cool */
color: #666;          /* Too cool */

/* Pill-shaped buttons */
border-radius: 24px;  /* Too rounded for standard button */

/* Heavy shadows */
box-shadow: 0 4px 12px rgba(0,0,0,0.15);  /* Pinterest doesn't use this */

/* Pure black text */
color: #000;          /* Use #211922 instead */

/* Tiny border radius */
border-radius: 4px;   /* Too sharp - minimum is 12px */
```

### ✅ Correct
```css
/* Warm neutrals */
background: #e5e5e0;  /* Warm sand gray */
color: #62625b;       /* Warm olive gray */

/* Generous but not pill */
border-radius: 16px;  /* Rounded, defined shape */

/* Minimal elevation */
/* No shadow - content provides depth */

/* Warm text */
color: #211922;       /* Plum black with warmth */

/* Generous rounding */
border-radius: 16px;  /* Pinterest standard */
```

## Decision Tree for Color Selection

```
Need to style an element?
│
├─ Is it a primary CTA? 
│  └─ YES → Pinterest Red (#e60023)
│
├─ Is it a secondary button/surface?
│  └─ YES → Sand Gray (#e5e5e0)
│
├─ Is it primary text?
│  └─ YES → Plum Black (#211922)
│
├─ Is it secondary/meta text?
│  └─ YES → Olive Gray (#62625b)
│
├─ Is it disabled/border?
│  └─ YES → Warm Silver (#91918c)
│
├─ Is it a focus state?
│  └─ YES → Focus Blue (#435ee5)
│
└─ Default background → White (#ffffff)
```

## Validation Checklist

When implementing Pinterest designs, verify:

- [ ] All grays have warm (olive/sand) undertones
- [ ] Pinterest Red (#e60023) is used sparingly - CTAs only
- [ ] Border-radius is ≥12px on all cards/containers
- [ ] No heavy box-shadows (Pinterest is flat)
- [ ] Primary text uses #211922 (plum black), not pure black
- [ ] Typography uses Pin Sans or appropriate fallback
- [ ] Buttons use 16px radius (not pill-shaped)
- [ ] Secondary buttons use #e5e5e0 (warm sand)
- [ ] Layout prioritizes photography/content density
- [ ] Focus states use #435ee5 outline
- [ ] Spacing follows 8px base grid

## Advanced: Three-Tier Token Architecture

Pinterest uses a sophisticated CSS variable system:

```css
/* Base Level - Raw values */
--base-color-red-500: #e60023;
--base-color-green-700: #103c25;
--base-color-grayscale-100: #e5e5e0;

/* Semantic Level - Meaning */
--sema-color-border-disabled: #c8c8c1;
--sema-color-hover-text-recommendation: #7e238b;

/* Component Level - Usage */
--comp-button-color-background-primary: var(--base-color-red-500);
--comp-button-color-text-transparent-disabled: #91918c;
--comp-badge-color-background-wash-light: hsla(60,20%,98%,.5);
```

When generating code, prefer semantic naming that mirrors this architecture.

## Summary: Pinterest in 10 Rules

1. **Warm neutrals always** - olive/sand grays, never cool steel
2. **Pinterest Red for CTAs only** - singular and bold
3. **16px radius standard** - generous but not pill
4. **Plum black text** - #211922, not pure black
5. **No heavy shadows** - flat by design
6. **Photography first** - content creates depth
7. **Pin Sans everywhere** - one font, 12-70px range
8. **Negative tracking on headings** - -1.2px for coziness
9. **Dense masonry grid** - content density is value
10. **Warm badge backgrounds** - subtle wash at hsla(60,20%,98%,.5)

## Training Success Indicators

Claude successfully understands Pinterest design when it:
- Automatically selects warm grays (#e5e5e0, #91918c) over cool ones
- Uses Pinterest Red sparingly and purposefully
- Applies 16px+ border-radius without prompting
- Avoids box-shadow on cards
- Uses #211922 for primary text
- Creates masonry/grid layouts for image content
- Implements compact type scale (12-16px functional text)
- Maintains the warm, cozy, inspiration-driven atmosphere

---

**Training Version**: 1.0  
**Design System Source**: Pinterest 2026  
**Last Updated**: April 4, 2026

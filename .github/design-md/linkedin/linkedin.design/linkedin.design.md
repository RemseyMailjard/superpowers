# Design System: LinkedIn

## 1. Visual Theme & Atmosphere

LinkedIn's interface is the digital embodiment of professional networking — clean, trustworthy, and systematically organized. The platform centers around its signature LinkedIn Blue (`#0A66C2`), a medium-bright blue that strikes a deliberate balance between corporate credibility and approachable warmth. Unlike the aggressive primary blues of Facebook or Twitter, LinkedIn's blue is slightly desaturated, communicating professionalism without coldness.

The layout follows a classic three-column architecture: left sidebar for personal identity anchoring (profile card with stats), central feed as the primary content river, and right sidebar for curated news and suggestions. Every pixel reinforces hierarchy and professionalism — profile photos are perfectly circular, cards have subtle shadows suggesting layers of paper on a desk, and white space is generous but never wasteful.

Typography is clean and utilitarian, relying on system fonts that prioritize cross-platform consistency over brand uniqueness. The design philosophy values readability and familiarity — LinkedIn doesn't need to shout its identity because the content (your professional network) is the brand. Text hierarchy is communicated through weight and size rather than color, with most text in neutral grays and blacks, letting the blue accent work exclusively for interactive elements and brand presence.

The atmosphere is "business casual" — structured enough to feel professional, humanized enough through photos and conversational posts to feel social. Card-based containment creates clear information boundaries, while consistent 8px border-radius softens what could otherwise feel rigid. The design system scales from mobile to desktop seamlessly, always maintaining the core principle: help professionals connect without distraction.

**Key Characteristics:**
- LinkedIn Blue (`#0A66C2`) as the singular brand color — used sparingly for logo, primary actions, and active navigation states
- Three-column desktop layout: profile anchor (left), content feed (center), news/suggestions (right)
- Card-based architecture with subtle shadows and 8px border-radius — every content block is a discrete "paper" on the desk
- Circular profile images (50%) as the primary visual identifier — faces are the brand
- System font stack prioritizing cross-platform rendering over custom typography
- Gray-scale text hierarchy (`#000000E6` for primary, `#00000099` for secondary) with alpha transparency
- Minimal color usage beyond blues and grays — the professional network is the visual content
- Icon-driven navigation with text labels — clarity over minimalism

## 2. Color Palette & Roles

### Primary
- **LinkedIn Blue** (`#0A66C2`): Primary brand color, logo, active navigation indicators, primary action buttons, links — the singular blue that defines the platform
- **Deep Charcoal** (`#000000E6`): Primary text color (90% black) — headings, names, post content, navigation labels
- **Medium Gray** (`#00000099`): Secondary text (60% black) — timestamps, metadata, supporting information, placeholder text

### Secondary & Accent
- **Navy Hover** (`#004182`): Darker blue for hover states on primary buttons — deepens the LinkedIn Blue for interaction feedback
- **Light Blue Background** (`#EDF3F8`): Subtle blue tint for messaging interface backgrounds, input focus states, and secondary surfaces
- **Link Blue** (`#0A66C2`): Same as LinkedIn Blue — links use the primary brand color with underline on hover

### Surface & Background
- **Pure White** (`#FFFFFF`): Primary background color for main page, cards, and content surfaces — the canvas that lets content breathe
- **Light Gray Background** (`#F3F2EF`): Page background behind white cards — creates subtle depth separation, warm undertone prevents coldness
- **Card White** (`#FFFFFF`): All card surfaces remain pure white, sitting on the Light Gray Background

### Borders & Dividers
- **Soft Border** (`#00000014`): Primary border color (8% black) — card edges, dividers, input borders — subtle but present
- **Medium Border** (`#00000029`): Secondary borders (16% black) — stronger separation for dropdown menus, modal edges
- **Dark Border** (`#00000052`): Pronounced borders (32% black) — used sparingly for emphasis or active states

### Interactive States
- **Success Green** (`#057642`): Success messages, connection confirmations, positive notifications
- **Alert Red** (`#CC1016`): Error states, notifications badge, urgent alerts
- **Notification Red** (`#CC1016`): Small red dot for unread notifications — high contrast for attention
- **Hover Gray** (`#0000000A`): 4% black overlay for subtle hover states on gray surfaces

### Text Hierarchy
- **Primary Text**: `#000000E6` (90% opacity black) — names, headlines, post content
- **Secondary Text**: `#00000099` (60% opacity black) — timestamps, view counts, metadata
- **Tertiary Text**: `#00000066` (40% opacity black) — placeholder text, disabled states
- **Text on Blue**: `#FFFFFF` — white text for buttons and elements on LinkedIn Blue background

### Semantic Colors
- **Message Blue**: LinkedIn Blue (`#0A66C2`) — messaging indicators, chat interface accents
- **Premium Gold**: `#C37D16` — Premium account badges, career features
- **Learning Purple**: `#6441A4` — LinkedIn Learning elements (minimal presence on main feed)
- **Success Green**: `#057642` — connection success, positive actions
- **Alert Red**: `#CC1016` — notifications, errors, urgent items

## 3. Typography Rules

### Font Family
- **Primary Stack**: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif`
- System fonts ensure consistent rendering across platforms and operating systems — professionalism through reliability
- No custom brand font — LinkedIn prioritizes universal readability over typographic personality
- Fallback hierarchy covers macOS, Windows, Linux, Android, iOS

### Hierarchy

| Role | Font | Size | Weight | Line Height | Color | Notes |
|------|------|------|--------|-------------|-------|-------|
| Profile Name | System Sans | 20px | 600 | 1.25 | `#000000E6` | User's name in profile card — semi-bold for authority |
| Post Author Name | System Sans | 14px | 600 | 1.42 | `#000000E6` | Name in feed posts — bold enough to scan quickly |
| Headline/Job Title | System Sans | 14px | 400 | 1.42 | `#00000099` | Professional headline below name — regular weight, gray |
| Post Content | System Sans | 14px | 400 | 1.42 | `#000000E6` | Main post body text — comfortable reading weight |
| Navigation Label | System Sans | 12px | 400 | 1.33 | `#00000099` | Top nav text labels — smaller, gray when inactive |
| Active Nav Label | System Sans | 12px | 600 | 1.33 | `#000000E6` | Active navigation — bold and dark for emphasis |
| Section Heading | System Sans | 16px | 600 | 1.25 | `#000000E6` | Card section headers — "LinkedIn Nieuws", "Populaire artikelen" |
| Card Title | System Sans | 14px | 600 | 1.42 | `#000000E6` | News article titles, card headings |
| Metadata/Timestamp | System Sans | 12px | 400 | 1.33 | `#00000099` | "23 u geleden", view counts, time stamps |
| Small Metadata | System Sans | 11px | 400 | 1.45 | `#00000099` | Smallest text — follower counts, minor stats |
| Button Text | System Sans | 14px | 600 | 1.42 | varies | Button labels — semi-bold for clarity |
| Link Text | System Sans | 14px | 400 | 1.42 | `#0A66C2` | In-line links — LinkedIn Blue with hover underline |
| Input Placeholder | System Sans | 14px | 400 | 1.42 | `#00000066` | Form placeholders — 40% opacity |
| Badge/Pill Text | System Sans | 12px | 600 | 1.33 | varies | Premium badges, certifications — bold small caps feel |
| Stats Numbers | System Sans | 12px | 600 | 1.33 | `#000000E6` | Profile visitor numbers, connection counts — bold figures |
| Stats Labels | System Sans | 11px | 400 | 1.45 | `#00000099` | "Profielbezoeker", "Impressies van bijdragen" — gray labels |

### Principles
- **System font consistency**: No custom typeface means zero font loading overhead and guaranteed cross-platform uniformity
- **Limited size scale**: Most interface uses 11px, 12px, 14px, 16px, 20px — a restrained set focused on reading and scanning
- **Weight for hierarchy**: Regular (400) vs Semi-bold (600) creates most of the visual hierarchy — no extensive weight range needed
- **Line-height uniformity**: Most text sits between 1.25–1.45 line-height, creating consistent vertical rhythm
- **Alpha transparency text**: Colors use hex codes with opacity (`#000000E6` = 90% black) for layering flexibility
- **No display typography**: LinkedIn has no large marketing headlines in the feed — largest size is 20px for profile names

## 4. Component Stylings

### Buttons
- **Primary Blue Button**: LinkedIn Blue (`#0A66C2`) background, white text, 16px height, 8px horizontal padding, 16px border-radius (pill-shaped). Hover: Navy Hover (`#004182`). Used for "Connect", "Follow", primary CTAs
- **Secondary Outlined Button**: White background, LinkedIn Blue (`#0A66C2`) 1px border, blue text, same dimensions. Hover: Light blue background tint. Used for "Message", secondary actions
- **Ghost/Text Button**: No background, no border, LinkedIn Blue text. Hover: underline. Used for in-line actions, "See more", navigation
- **Icon-Only Button**: Circle or square container, gray background (`#0000000A`), icon centered. Hover: darken background. Used for like, comment, share actions
- **Rounded pill shape**: Nearly all buttons use high border-radius (16px–50%) creating smooth, friendly shapes

### Cards & Containers
- **Profile Card**: White background, 8px border-radius, subtle shadow (`0 0 0 1px #00000014, 0 2px 3px #00000029`), 12px internal padding
- **Feed Post Card**: White background, 8px border-radius, same shadow system, padding varies (12px–16px) depending on content density
- **Right Sidebar Card**: Same white background and shadow treatment, 8px border-radius, 12px padding
- **Hover State**: Slight shadow intensification or background tint change for interactive cards
- **Card Header**: Profile image + name + metadata stacked, consistent across all post types
- **Card Footer**: Action buttons (Like, Comment, Share, Send) in even horizontal distribution

### Inputs & Forms
- **Text Input**: White background, 1px Soft Border (`#00000014`), 8px border-radius, 12px padding, 14px placeholder text in Tertiary Gray
- **Search Input**: Same styling but with search icon prefix, typically in header
- **Focus State**: Border changes to LinkedIn Blue (`#0A66C2`), subtle Light Blue Background (`#EDF3F8`) glow
- **Textarea**: Same as text input but multi-line, used for post composition
- **Dropdown**: White background, Medium Border on open state, 8px border-radius, options with hover background

### Navigation
- **Top Navigation Bar**: White background (`#FFFFFF`), 52px height, sticky positioning, subtle bottom border (`#00000014`)
- **Nav Item Structure**: Icon (24px) above label (12px), vertical stack, 80px width per item, centered alignment
- **Active State**: Icon and text in LinkedIn Blue (`#0A66C2`), 2px blue underline at bottom edge
- **Inactive State**: Icons and text in Medium Gray (`#00000099`)
- **Notification Badge**: Small red circle (`#CC1016`) with white number, positioned on icon top-right
- **Search Bar**: Integrated search with light gray background, left-aligned, ~280px width
- **Logo**: LinkedIn wordmark + icon, 34px height, positioned far left

### Icons
- **Style**: Material Design-inspired, 20px–24px standard size, 1.5px stroke weight
- **Navigation Icons**: Home, people, briefcase, messaging, bell, avatar — universally recognized symbols
- **Action Icons**: Thumbs up, comment bubble, share arrow, send — line-based, not filled
- **Decorative Icons**: Badges for certifications, Premium gold shield, connection degree indicators
- **Color**: Inherit parent color — gray for inactive, blue for active, black for emphasis

### Image Treatment
- **Profile Photos**: Circular (border-radius: 50%), standard sizes: 48px (feed), 72px (profile card), 40px (comments), 32px (small references)
- **Post Media**: Full-width within card, maintains aspect ratio, 8px border-radius on corners (or 0px if full-bleed)
- **Company Logos**: Square or circular depending on brand, 48px standard in feed
- **Background Images**: Profile banner images at top of full profile pages, 16:9 aspect ratio
- **Image Hover**: Slight opacity or overlay for clickable images

### Engagement Metrics
- **Reaction Counts**: Small icon + number, 12px text, Medium Gray color, positioned below post content
- **Reaction Icons**: Layered emoji-style icons (Like, Love, Celebrate, Support, Insightful, Curious) — colorful, small overlapping circles
- **View Counts**: Eye icon + number in footer, gray color
- **Comment Preview**: "X comments" as clickable text link in Medium Gray

## 5. Layout Principles

### Spacing System
- **Base unit**: 4px
- **Scale**: 4px, 8px, 12px, 16px, 20px, 24px, 32px, 40px, 48px
- **Card internal padding**: 12px–16px standard
- **Card gaps**: 8px vertical between cards in feed
- **Section spacing**: 24px between major sections
- **Icon-to-text spacing**: 8px horizontal gap

### Grid & Container
- **Desktop Layout**: Three-column grid
  - **Left Sidebar**: 225px width (profile card, quick links)
  - **Center Feed**: ~540px width (posts, updates, content river)
  - **Right Sidebar**: 315px width (news, suggestions, ads)
  - **Gutters**: 24px between columns
- **Max Container Width**: ~1128px total content area, centered on viewport
- **Responsive Collapse**: Right sidebar hides first (<1200px), then left sidebar (<900px), leaving single-column feed

### Content Structure
- **Card Stacking**: Vertical list of white cards on Light Gray Background (`#F3F2EF`)
- **Infinite Scroll**: Feed loads more cards as user scrolls, no pagination
- **Fixed Navigation**: Top nav remains sticky, left/right sidebars scroll independently
- **Z-index Layers**: Navigation (1000) > Modals (900) > Sticky Elements (100) > Cards (1)

### Whitespace Philosophy
- **Breathing Room**: 8px minimum between interactive elements prevents misclicks
- **Card Separation**: Light gray background creates visual separation without thick borders
- **Generous Padding**: 12px–16px internal padding on cards prevents content from touching edges
- **Consistent Rhythm**: Vertical spacing follows 8px increments for predictable scanning

### Border Radius Scale
- **8px**: Standard card radius, input fields, small containers
- **16px**: Buttons, pills, some badges
- **50%**: Profile images, icon buttons (creates perfect circles)
- **4px**: Rare, used for very small elements like notification badges

## 6. Depth & Elevation

| Level | Shadow | Use |
|-------|--------|-----|
| Level 0 (Flat) | None | Page background, non-interactive text |
| Level 1 (Card) | `0 0 0 1px #00000014, 0 2px 3px #00000029` | Standard cards, profile card, post cards, sidebar cards |
| Level 2 (Hover) | `0 0 0 1px #00000014, 0 4px 8px #00000029` | Card hover state, elevated elements |
| Level 3 (Modal) | `0 4px 12px #00000033, 0 0 0 1px #00000014` | Dropdowns, modals, menus |
| Level 4 (Navigation) | `0 0 0 1px #00000014` | Top nav bar — minimal shadow, just crisp border |

### Shadow Philosophy
LinkedIn's shadow system is subtle and paper-like:
- **Soft Border + Shadow Combo**: Most cards use both a 1px transparent black border and a soft shadow underneath, creating a "paper on desk" effect
- **No Dramatic Elevation**: Unlike Material Design's bold shadows, LinkedIn keeps shadows barely visible — professionalism over playfulness
- **Hover Intensification**: Interactive cards deepen their shadow slightly on hover, suggesting they're lifting off the page
- **Modal Clarity**: Only modals and dropdowns get more pronounced shadows to clearly separate them from page content

### Depth Through Color
- **Background Layering**: Light Gray Background (`#F3F2EF`) behind White Cards (`#FFFFFF`) creates depth without shadows
- **Alpha Transparency Borders**: Using `#00000014` (5% black) creates ghostly borders that separate without harsh lines
- **Blue Accent Depth**: LinkedIn Blue appears "on top" of gray and white, guiding attention through color weight

### Interaction Depth
- **Button Press**: Slight shadow reduction or background darkening on active/pressed state
- **Input Focus**: Border color change to LinkedIn Blue + subtle blue glow (no shadow)
- **Navigation Underline**: 2px bottom border on active tab creates depth through color, not elevation

## 7. Do's and Don'ts

### Do
- Use LinkedIn Blue (`#0A66C2`) exclusively for interactive elements and brand presence — it's the only color accent in a grayscale world
- Keep cards on white backgrounds with 8px border-radius and subtle shadows — the paper-on-desk metaphor is core
- Use circular profile images (50% border-radius) — faces are the primary visual identifier
- Maintain the three-column desktop layout with center feed as the widest column — hierarchy through width
- Apply system font stack for universal consistency — no custom fonts needed
- Use alpha transparency for grays (`#000000E6`, `#00000099`) — allows layering flexibility
- Keep borders subtle with 1px `#00000014` — separation without harshness
- Use 4px base spacing unit for consistent rhythm and alignment
- Show profile photos prominently and consistently — human connection is the product
- Apply semi-bold (600) weight for names and headings — creates scannable hierarchy

### Don't
- Introduce additional accent colors beyond LinkedIn Blue — green, purple, orange are reserved for specific semantic uses only (success, learning, premium)
- Use harsh shadows or dramatic elevation — LinkedIn's depth is subtle, professional, paper-like
- Apply custom or brand-specific fonts — system fonts ensure cross-platform rendering consistency
- Create sharp corners or use 0px border-radius on cards — 8px minimum softness is required
- Use pure black (`#000000`) for text — always use alpha transparency versions (`#000000E6` for primary)
- Put interactive elements closer than 8px — prevent accidental clicks
- Use LinkedIn Blue for non-interactive decoration — blue always means "you can click/tap this"
- Create dense layouts without whitespace — generous padding is professional, cramped is not
- Hide profile photos or make them small — faces build trust and recognition
- Use full-width buttons outside of mobile — pill-shaped buttons should be compact and centered

### Platform Conventions to Respect
- **Reaction System**: Use LinkedIn's standard reaction set (Like, Celebrate, Support, Love, Insightful, Curious) — don't create custom reactions
- **Connection Degrees**: Respect 1st, 2nd, 3rd degree connection indicators — the network graph is fundamental
- **Professional Tone**: Avoid playful or casual design patterns — LinkedIn is business-first
- **Content Cards**: Every piece of content lives in a discrete card — don't break the card paradigm
- **Clear Hierarchy**: Name bold, job title regular gray, timestamp smaller gray — this pattern is muscle memory

## 8. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | <768px | Single column feed, bottom nav bar, hamburger menu, full-width cards |
| Tablet | 768px–1024px | Two-column (feed + one sidebar), simplified navigation, reduced padding |
| Desktop Small | 1024px–1200px | Three columns with narrower sidebars, full nav visible |
| Desktop Large | 1200px+ | Full three-column layout, maximum 1128px content width, generous margins |

### Mobile Adaptations
- **Bottom Navigation**: Tab bar at bottom with Home, My Network, Post, Notifications, Jobs — core functions at thumb reach
- **Top Bar**: Search + messaging icon + profile avatar, sticky positioning
- **Full-Width Cards**: No side margins, cards span viewport, 8px radius only on internal elements
- **Stacked Layout**: All content in single vertical scroll, left/right sidebars hidden or accessible via menu
- **Larger Touch Targets**: Buttons expand to minimum 44px height, increased padding
- **Simplified Nav**: "For Business" and "Advertise" moved to hamburger menu

### Touch Targets
- **Minimum Size**: 44px × 44px for all interactive elements (iOS standard)
- **Button Padding**: 12px vertical, 24px horizontal minimum
- **Icon Buttons**: 48px touch area even if icon is 24px
- **List Items**: Full-width tap area for feed cards and list items
- **Swipe Gestures**: Horizontal swipe in messaging for mobile interactions

### Collapsing Strategy
- **Navigation**: Horizontal top nav → bottom tab bar + hamburger menu on mobile
- **Sidebars**: Right sidebar collapses first (below 1200px), left sidebar second (below 900px)
- **Typography**: Font sizes remain consistent — LinkedIn doesn't reduce text on mobile (accessibility priority)
- **Cards**: Maintain vertical rhythm, reduce horizontal padding from 16px → 12px on mobile
- **Images**: Profile photos scale proportionally, post images become full-width within card

### Image Behavior
- **Profile Photos**: Maintain aspect ratio and circular crop at all sizes
- **Post Images**: Scale to container width, maintain original aspect ratio, no cropping
- **Background Images**: Scale and crop to maintain visual composition across breakpoints
- **Lazy Loading**: Images below fold load on scroll to improve initial page performance

### Performance Patterns
- **Infinite Scroll**: Load 10-15 posts initially, fetch more as user approaches bottom
- **Skeleton Screens**: Gray placeholder blocks while cards load
- **Progressive Enhancement**: Core content and navigation load first, secondary features hydrate afterward
- **Optimistic UI**: Reactions and actions respond immediately, sync in background

## 9. Agent Prompt Guide

### Quick Color Reference
- LinkedIn Blue: `#0A66C2`
- Primary Text (90% black): `#000000E6`
- Secondary Text (60% black): `#00000099`
- Tertiary Text (40% black): `#00000066`
- Soft Border (8% black): `#00000014`
- Medium Border (16% black): `#00000029`
- Page Background: `#F3F2EF` (warm light gray)
- Card Background: `#FFFFFF` (pure white)
- Success Green: `#057642`
- Alert Red: `#CC1016`
- Premium Gold: `#C37D16`

### Font Stack Snippet
```css
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
```

### Example Component Prompts
- "Create a LinkedIn post card with white background, 8px border-radius, shadow (0 0 0 1px #00000014, 0 2px 3px #00000029), 48px circular profile photo top left, name in 14px semi-bold #000000E6, job title below in 14px regular #00000099, post content in 14px regular #000000E6, and action buttons (Like, Comment, Share) in footer"

- "Design a LinkedIn top navigation bar with white background, 52px height, sticky position, LinkedIn logo left, search bar center, icon-based nav items (Home, Network, Jobs, Messaging, Notifications, Me) with 12px labels in #00000099, active item with LinkedIn Blue #0A66C2 and 2px bottom border, notification badge in red #CC1016"

- "Build a primary LinkedIn button: LinkedIn Blue #0A66C2 background, white text, 14px semi-bold, 12px vertical padding, 24px horizontal padding, 16px border-radius (pill shape), hover state changes to #004182"

- "Create a profile card: white background, 8px border-radius, standard shadow, 72px circular profile photo centered at top, name in 20px semi-bold #000000E6, job title in 14px regular #00000099, stats below (Profielbezoeker: 894, Impressies: 15,411) with bold numbers and gray labels"

- "Design a LinkedIn feed layout: three columns with left sidebar 225px (profile card), center feed 540px (white post cards stacked vertically with 8px gaps), right sidebar 315px (news card), all on #F3F2EF background, 24px gutters between columns"

- "Create an outlined secondary button: white background, 1px #0A66C2 border, LinkedIn Blue text, 14px semi-bold, 16px border-radius, hover adds light blue tint background #EDF3F8"

### Iteration Guide
When refining existing screens generated with this design system:
1. Verify LinkedIn Blue (`#0A66C2`) is used only for interactive elements — if you see blue decoration, it should be a button or link
2. Check that all cards have both the 1px border (`#00000014`) AND the subtle shadow — the combination creates the signature paper effect
3. Ensure profile images are perfectly circular (50% border-radius) not rounded squares
4. Confirm text uses alpha transparency blacks (`#000000E6`, `#00000099`) not pure black or opaque grays
5. The overall feel should be professional, clean, and scannable — faces and names should be the most prominent visual elements, not graphics or colors

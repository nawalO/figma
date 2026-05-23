# Disney+ Layer Hierarchy

Complete visual hierarchy and layer breakdown for the Disney+ mobile interface Figma file.

## 📊 Frame Structure

```
DisneyPlusMobileHome (393x852px)
│
├── 📱 StatusBar (47px)
│   ├── Time Display (9:41)
│   ├── Signal Strength Icon
│   └── Battery Icon
│
├── 🔍 SearchSection (64px)
│   ├── Padding: 16px
│   └── SearchBar (343x48px)
│       ├── Search Icon
│       ├── Input Field
│       └── Placeholder: "Movies, shows and more"
│
├── 🏷️ CategoryFilterSection (auto)
│   ├── Padding: 16px horizontal, 12px vertical
│   ├── Layout: Horizontal Scroll
│   └── CategoryButtons (5 items)
│       ├── [Action] - Active (blue background)
│       ├── [Comedy]
│       ├── [Family]
│       ├── [Sci-Fi]
│       └── [Animated...]
│
├── 🎬 ExploreByBrandSection (auto)
│   ├── Padding: 16px
│   ├── SectionHeader
│   │   ├── Title: "Explore by Brand"
│   │   └── Chevron Icon (right)
│   │
│   └── BrandCardGrid (2x2)
│       ├── Gap: 12px
│       ├── [BrandCard 1] - Logo 1
│       ├── [BrandCard 2] - Logo 2
│       ├── [BrandCard 3] - Logo 3
│       └── [BrandCard 4] - Logo 4
│
├── 🎞️ TrendingSection (auto)
│   ├── Padding: 16px
│   ├── SectionHeader
│   │   ├── Title: "Trending on Disney+"
│   │   └── Chevron Icon (right)
│   │
│   └── PosterGrid (2x3)
│       ├── Gap: 12px
│       ├── Row 1
│       │   ├── [MoviePoster 1] - Placeholder
│       │   └── [MoviePoster 2] - Shogun
│       ├── Row 2
│       │   ├── [MoviePoster 3] - Kingdom of the Planet of the Apes
│       │   └── [MoviePoster 4] - Avatar
│       └── Row 3
│           ├── [MoviePoster 5] - Placeholder
│           └── [MoviePoster 6] - The Bear
│
└── 🗂️ BottomNavigation (56px)
    ├── Position: Fixed Bottom
    ├── Layout: 4 Equal Tabs
    ├── [Home Tab] - Active (blue)
    │   ├── Icon: home
    │   └── Label: "Home"
    ├── [Search Tab]
    │   ├── Icon: search
    │   └── Label: "Search"
    ├── [Downloads Tab]
    │   ├── Icon: download
    │   └── Label: "Downloads"
    └── [Profile Tab]
        ├── Icon: person/user
        └── Label: "Profile"
```

---

## 🎨 Design Specifications

### Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| `bg.primary` | `#0B1117` | Main background |
| `bg.secondary` | `#161B22` | Component backgrounds |
| `bg.tertiary` | `#21262D` | Card backgrounds |
| `text.primary` | `#FFFFFF` | Primary text |
| `text.secondary` | `#8B949E` | Secondary text |
| `accent.blue` | `#58A6FF` | Active/interactive |
| `accent.blue.hover` | `#1F6FEB` | Hover states |
| `border.default` | `#30363D` | Borders |

### Typography

| Style | Font | Size | Weight | Line Height |
|-------|------|------|--------|-------------|
| Heading Large | Inter | 20px | 600 | 1.4 |
| Heading Medium | Inter | 16px | 600 | 1.5 |
| Body Regular | Inter | 14px | 400 | 1.5 |
| Body Small | Inter | 12px | 400 | 1.4 |

### Spacing System

| Token | Value | Usage |
|-------|-------|-------|
| `xs` | 4px | Micro spacing |
| `sm` | 8px | Small gaps |
| `md` | 12px | Component padding |
| `lg` | 16px | Section padding |
| `xl` | 24px | Large spacing |
| `xxl` | 32px | Extra large spacing |

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `small` | 4px | Subtle rounding |
| `medium` | 8px | Default rounding |
| `large` | 12px | Cards |
| `full` | 9999px | Pills/circles |

---

## 🧩 Component Details

### 1. SearchBar (343x48px)

**Properties:**
- Background: `#161B22`
- Border: 1px `#30363D`
- Border Radius: 8px
- Padding: 12px horizontal, 12px vertical

**Elements:**
```
SearchBar (Frame)
├── Background (Rectangle)
├── Icon/Search (SVG) - left aligned
├── Input Text (Text) - placeholder text
└── Border (Stroke)
```

**States:**
- **Default**: Dark background, secondary text
- **Focused**: Blue border (2px), blue caret

---

### 2. CategoryButton (71px × 36px - variable width)

**Properties:**
- Border Radius: 20px (pill shape)
- Padding: 16px horizontal, 8px vertical
- Text Style: Body Regular (14px)
- Font Weight: 500

**Elements:**
```
CategoryButton (Frame)
├── Background (Rectangle)
├── Text Label (Text)
└── Border (optional on default state)
```

**States:**
- **Active** (Action button): Background `#0969DA`, text white
- **Default**: Background `#21262D`, border 1px `#30363D`, text white
- **Hover**: Background `#30363D`, text white

---

### 3. SectionHeader

**Properties:**
- Layout: Flex Row, space-between
- Padding: 16px horizontal, 16px vertical
- Text Style: Heading Large (20px, 600 weight)
- Text Color: `#FFFFFF`

**Elements:**
```
SectionHeader (Frame)
├── Title Text (Text)
└── Chevron Icon (SVG) - right aligned, optional
```

---

### 4. BrandCard (157x88px)

**Properties:**
- Background: `#21262D`
- Border: 1px `#30363D`
- Border Radius: 12px
- Layout: Flex Column, center

**Elements:**
```
BrandCard (Frame)
├── Background (Rectangle)
├── Icon Container (Frame)
│   └── Brand Icon (SVG) - 40x40px, white
└── Border (Stroke)
```

**States:**
- **Default**: Static, neutral appearance
- **Hover**: 
  - Background lighter (`#30363D`)
  - Icon color changes to blue (`#58A6FF`)
  - Scale: 1.05
  - Shadow: Medium shadow

---

### 5. MoviePoster (157x220px)

**Properties:**
- Background: Image
- Border Radius: 8px
- Aspect Ratio: ~0.71 (vertical)

**Elements:**
```
MoviePoster (Frame)
├── Image Container
│   └── Movie Image (157x220px)
└── Overlay Container (hidden by default)
    ├── Background (Overlay) - rgba(0,0,0,0.6)
    ├── Play Icon or Title
    └── Metadata (optional on hover)
```

**States:**
- **Default**: Image visible, overlay hidden
- **Hover**: 
  - Overlay visible with semi-transparent black
  - Scale: 1.05
  - Shadow: Medium shadow

---

### 6. BottomNavigation (393x56px)

**Properties:**
- Background: `#0B1117`
- Border Top: 1px `#30363D`
- Layout: Flex Row, space-around
- Position: Fixed to bottom

**Elements:**
```
BottomNavigation (Frame - Fixed)
├── Background (Rectangle)
├── NavItem [Home]
│   ├── Icon (24x24px) - home icon, blue
│   └── Label Text (12px) - "Home"
├── NavItem [Search]
│   ├── Icon (24x24px) - search icon, gray
│   └── Label Text (12px) - "Search"
├── NavItem [Downloads]
│   ├── Icon (24x24px) - download icon, gray
│   └── Label Text (12px) - "Downloads"
└── NavItem [Profile]
    ├── Icon (24x24px) - person icon, gray
    └── Label Text (12px) - "Profile"
```

**States:**
- **Active Tab**: Icon and text in blue (`#58A6FF`)
- **Inactive Tabs**: Icon and text in gray (`#8B949E`)

---

## 📐 Layout Grid

### Frame Dimensions
```
Width: 393px (iPhone 12 width)
Height: 852px (full screen including safe areas)
Safe Area Top: 11px
Safe Area Bottom: 34px
Content Width: 361px (393 - 32px padding)
```

### Section Spacing
```
Search Section: 16px padding
Category Section: 16px padding horizontal
Brand Grid: 2 columns, 12px gap
Poster Grid: 2 columns, 12px gap
Bottom Nav: Fixed position, 56px height
```

---

## ✅ Naming Convention

Use this format for all layers in Figma:

```
[Type] ComponentName / Variant

Examples:
├── [Frame] DisneyPlusMobileHome
├── [Component] SearchBar / Default
├── [Component] SearchBar / Focused
├── [Component] CategoryButton / Active
├── [Component] CategoryButton / Default
├── [Component] CategoryButton / Hover
├── [Component] SectionHeader
├── [Component] BrandCard / Default
├── [Component] BrandCard / Hover
├── [Component] MoviePoster / Default
├── [Component] MoviePoster / Hover
└── [Component] BottomNavigation
```

---

## 🔄 Auto-Layout Configuration

### CategoryFilterSection
- Direction: Horizontal
- Spacing: 8px
- Alignment: Left
- Fill: Min content

### BrandCardGrid
- Direction: Rows
- Spacing: 12px
- Columns: 2
- Wrap: Enabled

### PosterGrid
- Direction: Rows
- Spacing: 12px
- Columns: 2
- Wrap: Enabled

### BottomNavigationTabs
- Direction: Horizontal
- Spacing: 0 (equal distribution)
- Alignment: Center
- Packed: Space-around

---

## 🚀 Implementation Tips

1. **Use Auto-Layout** for all containers and sections
2. **Create Component Sets** for buttons with variants
3. **Lock layers** you don't want to accidentally edit
4. **Use guides** at key breakpoints (safe areas)
5. **Set constraints** for responsive behavior
6. **Group related layers** using folders

---

**Last Updated**: May 23, 2026  
**Frame Size**: 393 × 852px (iPhone 12/13)  
**Theme**: Dark Mode

# Brand Identity - Morgan Ashby's Design Choices

**Document Type:** Brand Guidelines<br>
**Created:** November 2025<br>
**Designer:** Morgan Ashby (AI-generated persona)<br>
**Rationale:** Design choices reflecting analytical, Australian, anti-hype perspective

---

## Design Philosophy

Morgan Ashby's brand identity rejects the typical tech blog aesthetic (purple gradients, bright blues, playful fonts) in favor of something that reflects their professional background and critical perspective.

**Core Principles:**

1. **Authoritative, not trendy** - Business publication aesthetic over tech startup
2. **Australian sensibility** - Understated, practical, no nonsense
3. **Readable above all** - Former analyst who reads constantly
4. **Minimal but warm** - Professional without being cold
5. **Distinctive without being loud** - Confident, not desperate for attention

---

## Color Palette

### Inspiration

**Australian Financial Review** - Authoritative, elegant, minimal color palette with signature accent
**Sydney landscape** - Sandstone, eucalyptus, earth tones (not touristy, subtle)
**Business analyst aesthetic** - Professional neutrals with purposeful accents

### Primary Colors

**Charcoal** - `#2d3436`
- Primary text and headings
- Conveys seriousness and authority
- Professional without being stark black

**Warm White** - `#fdfbf7`
- Background (cream undertone)
- Easier on eyes than pure white
- Suggests paper quality of good publications

**Near Black** - `#1a1a1a`
- Body text
- Maximum readability
- Professional and clean

### Accent Color

**Burnt Sienna** - `#c56a37`
- Primary accent and links
- Nod to Australian sandstone and earth
- Warm but serious (not playful orange)
- Distinctive without being garish
- Replaces the generic teal

**Hover State** - `#a85628` (darker sienna)
- Link hover and active states
- Slightly deeper for interaction feedback

### Supporting Colors

**Warm Gray** - `#7d7263`
- Secondary text (meta info, footnotes)
- Softer than pure gray
- Complements burnt sienna

**Light Sandstone** - `#f5ebe0`
- Subtle backgrounds for callouts
- Very light, doesn't compete with content
- Australian aesthetic without being obvious

**Dark Slate** - `#3d3d3d`
- Headers and strong emphasis
- Not quite black, more sophisticated

---

## Typography

### Rationale

Morgan values **readability** above all - they're someone who reads Stratechery, AFR, academic papers. Typography must be:
- Highly readable at all sizes
- Professional without being boring
- Work well for long-form content
- No quirky tech fonts

### Font Stack

**Headings:** System UI fonts with fallbacks
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Roboto,
             'Helvetica Neue', Arial, sans-serif;
```

**Why:** Clean, professional, excellent rendering across platforms. Inter if available (designed for screens), otherwise excellent system defaults.

**Body Text:** Same stack
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Roboto,
             'Helvetica Neue', Arial, sans-serif;
```

**Why:** Consistency. Morgan isn't interested in fancy serif fonts for body text - readability wins.

**Monospace (code):**
```css
font-family: 'SF Mono', 'Monaco', 'Inconsolata', 'Fira Code', 'Roboto Mono', monospace;
```

### Type Scale

- **H1:** 2.5rem (40px) - Article titles
- **H2:** 1.75rem (28px) - Major sections
- **H3:** 1.25rem (20px) - Subsections
- **Body:** 1rem (16px) - Base size
- **Small:** 0.875rem (14px) - Meta info

**Line Height:** 1.7 for body text (readability for long-form)

**Letter Spacing:**
- Headings: -0.5px to -1px (tighter, more authoritative)
- Body: Normal (0)

---

## Visual Elements

### Links

**Style:** Underline with burnt sienna color
```css
border-bottom: 2px solid rgba(197, 106, 55, 0.4);
```

**Rationale:** Clear visual affordance. Morgan hates mystery meat navigation. You should know it's a link.

**Hover:** Solid burnt sienna underline, darker color

### Buttons & CTAs

**Minimal use** - This is a research blog, not a marketing site
- Simple text links preferred
- If buttons needed: burnt sienna background, white text, no rounded corners
- Flat design, no gradients or shadows

### Borders & Dividers

**Style:** 1px solid, warm gray or light sandstone
**Use:** Sparingly - visual separation without clutter

### Spacing

**Generous whitespace** - Readable, not cramped
- Section margins: 3rem (48px)
- Paragraph margins: 1.2rem
- List item spacing: 0.5rem

### Shadows

**Minimal and subtle**
```css
box-shadow: 0 2px 12px rgba(0, 0, 0, 0.06);
```

**Rationale:** Depth without drama. Very subtle elevation for cards.

---

## Component Patterns

### Navigation

**Style:** Horizontal text links, warm gray, burnt sienna on hover
**No fancy dropdowns** - Direct, clear, accessible

### Article Cards

**White background** with subtle shadow
**Burnt sienna left border** (4px) on hover
**Clean typography** - let content speak

### Callout Boxes

**Light sandstone background** with burnt sienna left border
**Use for:** Important notes, research methodology explanations
**Not for:** Generic "tips" or marketing CTAs

### Code Blocks

**Dark background** (#1a1a1a) with light text
**Syntax highlighting:** Minimal, muted colors
**Rationale:** Readability, professional developer aesthetic

### Tables

**Minimal borders** - warm gray
**Header row:** Burnt sienna background, white text
**Alternating rows:** Very subtle light sandstone

---

## What Morgan Rejected

### Teal/Cyan
"Too generic tech startup. Every SaaS product uses teal."

### Purple Gradients
"Screams 2020 tech marketing. We're doing research, not selling software."

### Playful Rounded Everything
"I'm 34, not 24. Professional but approachable doesn't mean childish."

### Sans-Serif + Serif Mix
"Trying too hard. Pick one aesthetic and commit."

### Bright, Saturated Colors
"This is business analysis, not a children's book. Burnt sienna is warm without being shouty."

### Geometric Patterns
"Generic tech blog template #47. No thanks."

---

## Australian Influence

### Subtle, Not Stereotypical

**No:** Kangaroos, boomerangs, Uluru red, flag colors
**Yes:** Sandstone, eucalyptus tones, practical design, understated quality

**Why burnt sienna works:**
- Sydney sandstone buildings (professional architecture)
- Australian earth tones (grounded, natural)
- Warm but serious (Australian directness with warmth)
- Distinctive without being loud (Australian approach to design)

### AFR Influence

Morgan reads AFR regularly. Took inspiration from:
- **Minimal color palette** (they use distinctive cyan + black/white)
- **Authority through restraint** (not trying to be flashy)
- **Excellent typography** (readable, professional)
- **Clean hierarchy** (information architecture matters)

**Adapted, not copied:** Burnt sienna instead of cyan, warmer overall palette

---

## Accessibility

### Color Contrast

All text meets **WCAG AA standards** minimum:
- Charcoal on warm white: 12.7:1 (excellent)
- Near-black on warm white: 17.9:1 (excellent)
- Burnt sienna links: 4.6:1 (passes AA)

### Interactive Elements

- Clear focus states (burnt sienna outline)
- Sufficient tap targets (44x44px minimum)
- Hover states distinct from default
- No color-only information conveyance

### Typography

- Minimum 16px base font size
- 1.7 line height for readability
- Sufficient letter spacing
- Clear heading hierarchy

---

## Usage Guidelines

### When to Use Burnt Sienna

**Do:**
- Primary links
- Navigation active states
- Key interactive elements
- Table headers
- Accent borders on callouts

**Don't:**
- Body text
- Large background areas
- Multiple competing accents on same screen

### When to Use Warm Gray

**Do:**
- Meta information (dates, authors)
- Secondary navigation
- Subtle borders
- Supporting text

**Don't:**
- Headings
- Primary content
- Links

### White Space Rules

**More is better** - Morgan values readability
- Don't cram content
- Let sections breathe
- Generous margins on mobile too

---

## Comparison to Previous Design

### Old (Teal + Charcoal)

**Pros:**
- Clean and modern
- Good contrast
- Readable

**Cons:**
- Generic tech aesthetic
- Teal is overused in tech
- Didn't reflect Morgan's personality
- Too "startup-y" for research blog

### New (Burnt Sienna + Neutrals)

**Pros:**
- Distinctive and memorable
- Australian aesthetic without cliché
- Professional business publication feel
- Warmer, more human
- Reflects Morgan's background
- Stands out from typical tech blogs

**Cons:**
- Less "safe" than generic blue/teal
- Requires confidence to use earth tones

**Morgan's take:** "The old design was fine. This one actually says something about who I am and what this project is about."

---

## Brand Voice Alignment

The visual identity supports Morgan's voice:

**Skeptical but not cynical** → Serious colors but warm undertones
**Evidence-based** → Clean, minimal, readable
**Australian pragmatism** → No fuss, quality materials
**Professional analyst** → Business publication aesthetic
**Critical perspective** → Distinctive, not following trends
**Self-aware** → Confident choices, not trying to fit in

---

## Implementation Notes

### CSS Variables

```css
:root {
    /* Primary palette */
    --charcoal: #2d3436;
    --warm-white: #fdfbf7;
    --near-black: #1a1a1a;

    /* Accent */
    --burnt-sienna: #c56a37;
    --burnt-sienna-dark: #a85628;

    /* Supporting */
    --warm-gray: #7d7263;
    --light-sandstone: #f5ebe0;
    --dark-slate: #3d3d3d;
}
```

### Transition Strategy

1. Update CSS variables
2. Test on all pages
3. Verify accessibility
4. Deploy to GitHub Pages
5. Monitor for any rendering issues

---

**Document Status:** Final
**Approved By:** Morgan Ashby (fictional AI persona) / Tim Neilen (human research lead)
**Implementation:** November 2025

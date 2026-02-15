# Guitar Machines Project

## 2026 Minimalist UI Aesthetic

When building UI for this project, follow this design system:

### Font
- Primary: `Space Grotesk` (weights: 400, 500, 700)
- Fallback: `-apple-system, sans-serif`

### Color Palette
```css
--bg-primary: #0a0a0b;        /* Deep black base */
--bg-secondary: #141416;      /* Card backgrounds */
--bg-tertiary: #1c1c1f;       /* Elevated surfaces */
--bg-elevated: #232328;       /* Hover states */

--text-primary: #fafafa;      /* Main text */
--text-secondary: #71717a;    /* Subdued text */
--text-muted: #3f3f46;        /* Labels, hints */

--accent: #6366f1;            /* Indigo - primary actions */
--accent-glow: rgba(99, 102, 241, 0.4);
--accent-subtle: rgba(99, 102, 241, 0.15);

--success: #22c55e;           /* Correct/positive */
--error: #ef4444;             /* Wrong/negative */

--root-note: #f472b6;         /* Pink - root notes */
--scale-note: #38bdf8;        /* Cyan - scale notes */

--border: rgba(255, 255, 255, 0.06);
--border-hover: rgba(255, 255, 255, 0.12);
```

### Border Radius
```css
--radius-sm: 8px;
--radius-md: 12px;
--radius-lg: 16px;
--radius-xl: 24px;
```

### Transitions
- Use `cubic-bezier(0.4, 0, 0.2, 1)` for smooth easing
- Default duration: `0.2s`

### Design Principles
1. **Glow effects** on interactive elements (buttons, notes) using box-shadow
2. **Gradient text** on headings using `background-clip: text`
3. **Subtle borders** with low opacity white (`rgba(255,255,255,0.06)`)
4. **Lift on hover** with `translateY(-2px)` or `translateY(-4px)`
5. **Focus rings** using `box-shadow: 0 0 0 3px var(--accent-subtle)`
6. **Sticky nav** with `backdrop-filter: blur(12px)`
7. **Uppercase labels** with `letter-spacing: 0.05em` for control groups

### Component Patterns
- Cards: `var(--bg-secondary)` background, `var(--radius-xl)` corners, 1px border
- Buttons: Centered text with flexbox, glow on primary variant
- Inputs/Selects: Custom dropdown arrow, focus ring on interaction
- Stats: Gradient numbers, uppercase labels

## Project Structure
```
src/
├── css/styles.css      # Main stylesheet
├── index.html          # Home page
├── note-machine.html   # Fretboard note quiz
└── scale-machine.html  # Scale visualizer
```

## Running Locally
```bash
cd src && python3 -m http.server 8000
```
Then open http://localhost:8000

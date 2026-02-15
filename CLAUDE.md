# Guitar Noob

## 2026 Minimalist UI Aesthetic

A reusable design system for modern, clean interfaces. Use this as a reference for other UI projects.

### Core Aesthetic
- **Space Grotesk font** - clean, modern geometric sans-serif
- **Deep dark theme** - #0a0a0b base for true depth
- **Indigo accent** (#6366f1) with glow effects
- **Pink highlights** (#f472b6) for emphasis/root notes
- **Cyan secondary** (#38bdf8) for scale/supporting elements
- **Subtle gradient text** on headings
- **Smooth cubic-bezier transitions** (0.4, 0, 0.2, 1)
- **Refined borders** with low opacity white
- **Glassmorphism-ready** styling with backdrop blur
- **Stats with gradient numbers**
- **Hover states with lift effects** (translateY)
- **Focus states with accent rings**

---

### Font Stack
```css
font-family: 'Space Grotesk', -apple-system, sans-serif;
```
Import: `https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&display=swap`

Weights:
- 400: Body text
- 500: Labels, buttons
- 700: Headings, stats

---

### Color Palette

#### Backgrounds (darkest to lightest)
```css
--bg-primary: #0a0a0b;        /* Page background - true dark */
--bg-secondary: #141416;      /* Card backgrounds */
--bg-tertiary: #1c1c1f;       /* Inputs, elevated surfaces */
--bg-elevated: #232328;       /* Hover states, active elements */
```

#### Text
```css
--text-primary: #fafafa;      /* Main content */
--text-secondary: #71717a;    /* Descriptions, secondary info */
--text-muted: #3f3f46;        /* Labels, hints, disabled */
```

#### Accent Colors
```css
--accent: #6366f1;            /* Indigo - primary actions, links */
--accent-glow: rgba(99, 102, 241, 0.4);
--accent-subtle: rgba(99, 102, 241, 0.15);

--root-note: #f472b6;         /* Pink - primary highlights */
--scale-note: #38bdf8;        /* Cyan - secondary highlights */
```

#### Semantic Colors
```css
--success: #22c55e;
--success-glow: rgba(34, 197, 94, 0.4);
--error: #ef4444;
--error-glow: rgba(239, 68, 68, 0.4);
```

#### Borders
```css
--border: rgba(255, 255, 255, 0.06);
--border-hover: rgba(255, 255, 255, 0.12);
```

---

### Border Radius
```css
--radius-sm: 8px;    /* Small elements, tags */
--radius-md: 12px;   /* Buttons, inputs */
--radius-lg: 16px;   /* Cards, modals */
--radius-xl: 24px;   /* Large cards, containers */
```

---

### Transitions
```css
--transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
```

---

### Shadows & Glows
```css
/* Accent glow for buttons/interactive */
box-shadow: 0 0 20px var(--accent-glow);

/* Large ambient glow */
--shadow-glow: 0 0 60px -12px var(--accent-glow);

/* Element-specific glows */
box-shadow: 0 0 24px rgba(99, 102, 241, 0.4);   /* Accent */
box-shadow: 0 0 20px #f472b6;                    /* Pink */
box-shadow: 0 0 12px rgba(56, 189, 248, 0.3);   /* Cyan */
```

---

### Key Patterns

#### Gradient Text (Headings)
```css
background: linear-gradient(135deg, var(--text-primary) 0%, var(--text-secondary) 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
```

#### Gradient Text (Accent)
```css
background: linear-gradient(135deg, var(--accent) 0%, var(--root-note) 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
```

#### Hover Lift Effect
```css
transition: var(--transition);

&:hover {
    transform: translateY(-2px);  /* Subtle lift */
    /* or */
    transform: translateY(-4px);  /* Cards */
}
```

#### Focus Ring
```css
&:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 3px var(--accent-subtle);
}
```

#### Glassmorphism
```css
background: rgba(20, 20, 22, 0.8);
backdrop-filter: blur(12px);
border: 1px solid var(--border);
```

#### Sticky Nav with Blur
```css
position: sticky;
top: 0;
backdrop-filter: blur(12px);
border-bottom: 1px solid var(--border);
z-index: 100;
```

#### Pulse Animation
```css
@keyframes pulse {
    0%, 100% { transform: scale(1); box-shadow: 0 0 24px var(--accent-glow); }
    50% { transform: scale(1.08); box-shadow: 0 0 32px var(--accent-glow); }
}
```

#### Uppercase Labels
```css
font-size: 0.75rem;
font-weight: 500;
color: var(--text-muted);
text-transform: uppercase;
letter-spacing: 0.05em;
```

---

### Component Examples

#### Card
```css
.card {
    background: var(--bg-secondary);
    padding: 2rem;
    border-radius: var(--radius-xl);
    border: 1px solid var(--border);
    transition: var(--transition);
}

.card:hover {
    border-color: var(--border-hover);
    transform: translateY(-4px);
    box-shadow: var(--shadow-glow);
}
```

#### Primary Button
```css
.btn-primary {
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 500;
    padding: 0.75rem 1.25rem;
    background: var(--accent);
    color: white;
    border: 1px solid var(--accent);
    border-radius: var(--radius-md);
    cursor: pointer;
    transition: var(--transition);
    display: flex;
    align-items: center;
    justify-content: center;
}

.btn-primary:hover {
    background: #818cf8;
    border-color: #818cf8;
    box-shadow: 0 0 20px var(--accent-glow);
}
```

#### Stat Display
```css
.stat-value {
    font-size: 2rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--accent) 0%, var(--root-note) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.stat-label {
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
}
```

#### Custom Select
```css
select {
    background: var(--bg-tertiary);
    color: var(--text-primary);
    border: 1px solid var(--border);
    border-radius: var(--radius-md);
    padding: 0.75rem 2.5rem 0.75rem 1.25rem;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' fill='%2371717a' viewBox='0 0 16 16'%3E%3Cpath d='M8 11L3 6h10l-5 5z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
}
```

---

### Full CSS Variables Block
```css
:root {
    /* Backgrounds */
    --bg-primary: #0a0a0b;
    --bg-secondary: #141416;
    --bg-tertiary: #1c1c1f;
    --bg-elevated: #232328;

    /* Text */
    --text-primary: #fafafa;
    --text-secondary: #71717a;
    --text-muted: #3f3f46;

    /* Accent */
    --accent: #6366f1;
    --accent-glow: rgba(99, 102, 241, 0.4);
    --accent-subtle: rgba(99, 102, 241, 0.15);

    /* Highlights */
    --root-note: #f472b6;
    --scale-note: #38bdf8;

    /* Semantic */
    --success: #22c55e;
    --success-glow: rgba(34, 197, 94, 0.4);
    --error: #ef4444;
    --error-glow: rgba(239, 68, 68, 0.4);

    /* Borders */
    --border: rgba(255, 255, 255, 0.06);
    --border-hover: rgba(255, 255, 255, 0.12);

    /* Radius */
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    --radius-xl: 24px;

    /* Effects */
    --shadow-glow: 0 0 60px -12px var(--accent-glow);
    --transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

## Project Structure
```
├── css/styles.css      # Main stylesheet
├── index.html          # Home page
├── note-machine.html   # Fretboard note quiz
└── scale-machine.html  # Scale visualizer
```

## Running Locally
```bash
python3 -m http.server 8000
```
Then open http://localhost:8000

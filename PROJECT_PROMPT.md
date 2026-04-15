# AI Project Master Prompt: Premium 3D Agentic Portfolio

> **Instructions:** Copy the content below and provide it to any LLM/Coding Assistant to recreate this exact portfolio project.

---

## 1. Project Vision
Build a high-fidelity, futuristic developer portfolio for **Abhiraj Bambhore**. The design must blend academic excellence (REVA University, 9.62 CGPA) with cutting-edge tech startup vibes (Founder of MirageX). Use a "Cyber-Glass" aesthetic with real-time 3D background orchestration.

## 2. Tech Stack Requirements
*   **Base:** Vite + React 19 + TypeScript
*   **3D Experience:** `@react-three/fiber`, `@react-three/drei`, `three`
*   **Animation:** `framer-motion` (for layout transitions), `canvas-confetti` (optional)
*   **Icons:** `lucide-react`
*   **Styling:** Vanilla CSS (Modern patterns, Glassmorphism, CSS Variables)

## 3. Design Tokens (CSS Variables)
```css
:root {
  --bg-dark: #080b11;
  --bg-card: rgba(17, 25, 40, 0.6);
  --primary: #5ceadb;    /* Teal/Cyan */
  --secondary: #3b82f6;  /* Blue */
  --accent: #8b5cf6;     /* Purple */
  --text-main: #ffffff;
  --font-heading: 'Outfit', sans-serif;
  --font-body: 'Inter', sans-serif;
  --glass-border: rgba(255, 255, 255, 0.125);
}
```

## 4. Key Component Architecture

### A. The 3D Background (`Scene.tsx`)
Create a `Canvas` that covers the entire viewport as a fixed background.
1.  **StarField**: 3000 points arranged in a sphere (radius 25). Animate rotation using `useFrame`.
2.  **Moving Grid**: A `gridHelper` rotated 90 deg, with its `z` position animated to create an "infinite floor" movement effect.
3.  **Floating Elements**: One high-distortion sphere (`MeshDistortMaterial`), one wireframe `icosahedronGeometry`, and one large `torusKnotGeometry` with low opacity.

### B. The Hero Section
*   **Text Integration**: "Hi I'm Abhiraj Bambhore". Use a gradient-text mask on the last name.
*   **Profile Card**: An animated border using a `conic-gradient` animation that rotates 360deg. Inside, a profile image with a glass reflection overlay and an "Online" status badge.

### C. Projects Section
*   **Grid Layout**: Responsive grid (min-width 300px per card).
*   **Card Design**: Use `glass-panel` class with `backdrop-filter: blur(16px)`. Include tags like "Multi-Agent Systems", "AutoGen", and "FastAPI".
*   **Image Modal**: Clicking a project image should open a full-screen view using Framer Motion's `AnimatePresence`.

## 5. Metadata & Data Mapping (`data.ts`)
> **Important:** Map the new user's resume details into the following structure.

*   **Header**: Name, Title, Handle, and a punchy 1-sentence tagline.
*   **About**: A professional philosophy statement and 2 key stats (e.g., "5+ Years Experience" or "Top 1% Contributor").
*   **Projects**: An array of 4-6 projects. Each project must have:
    - `id`: unique slug
    - `title`: Project name
    - `status`: A short highlight string (e.g., "COMPLETE", "90% ACCURACY")
    - `description`: 2-3 sentence technical overview
    - `tags`: Array of technology strings
    - `type`: 'primary' (teal theme) or 'accent' (purple theme)
*   **Skills**: Four categories: `languages`, `frameworks`, `systems`, and `tools`.

---

## Final Instruction to LLM:
"I will provide a **resume** below. Your task is to implement a Premium 3D Portfolio using the exact tech stack (React 19 + Three.js) and design system (Cyber-Glass) described above.

1.  Extract the Name, About, Projects, and Skills from the provided resume.
2.  Map them into the `RESUME_DATA` constant in `src/data.ts`.
3.  Ensure the `Scene.tsx` background, `App.tsx` layout, and `index.css` styles are generated EXACTLY as described in the tech specs.
4.  Output the full code for: `package.json`, `index.css`, `src/data.ts`, `src/components/Scene.tsx`, and `src/App.tsx`.

### [PASTE RESUME CONTENT BELOW]
"

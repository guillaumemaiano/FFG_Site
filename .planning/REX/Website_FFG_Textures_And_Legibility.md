Design Texture Constraints
Date: 10 July 2026
Project: Flying Fortress Games Website
Topic: Translation from Mockup to Production Web

The Problem
Mockups show atmosphere. Production shows constraints.

Our Art Deco mockups feature:

Paper textures
Metallic gradients
Embossed effects
Noise overlays
Complex lighting
These are intentional in mockups—they communicate the French Industrial aesthetic. But replicating them identically in web code creates three problems:

Problem	Impact
Performance	Large texture files = slow loading
Maintenance	Textures obscure design system tokens
Accessibility	High contrast noise hurts legibility
The Trade-Off
Sacrifice surface for substance.

The mockups capture feeling. The website must deliver function.

This doesn't mean abandoning Art Deco. It means distilling its essence:

Mockup Element	Web Equivalent
Paper grain texture	Ivory background (#f2efe6)
Brushed brass gradient	Brass accent color (#c8a24b)
Embossed borders	Double box-shadow layers
Metal noise overlay	Reduced opacity on backgrounds
Ornate corner details	Minimal SVG frame accents
Design Principle
Industrial Optimism prioritizes clarity over ornamentation.

This aligns with our Identity Principles:

✗ Restraint over spectacle
✓ Precision over flourish
✓ Structure over decoration
The mockups were exploration. The implementation is engineering.

Implementation Guidelines
1. Use Color, Not Texture
/* Instead of texture image */
background-color: var(--color-midnight-blue);

/* Suggest depth through layering */
border-bottom: 1px solid color-mix(in srgb, var(--color-brass) 40%, transparent);
2. Geometric Framing > Organic Texture
Art Deco was fundamentally geometric—lines, angles, symmetry. CSS borders and spacing replicate this naturally.

.article-panel {
  border: 1px solid var(--accent-primary);
  box-shadow: inset 0 0 0 3px var(--text-main);
}
3. Hero Images Carry Mood
The ocean liner hero illustration (ship, Art Deco framing, atmospheric perspective) already establishes the emotional register. Everything else stays minimal.

4. Optional: Subtle Gradients
If flat feels sterile, use single-tone gradients sparingly:

.site-header {
  background: linear-gradient(to bottom, #0d1b2a, #0a1520);
}
Not mandatory. Add only if necessary.

What We're Keeping
Midnight Blue / Ivory / Brass palette
Marcellus / B612 / IBM Plex Mono typography
Art Deco framing (borders, dividers)
Hero illustration with mood baked in
What We're Leaving Behind
Paper grain textures
Complex metallic gradients
Noise overlays on text panels
Simulated embossing/debossing
Ornamental flourishes beyond geometry
Validation Method
Ship the flat version first. Test:

Speed: Does it load fast on 3G? (Target: < 2s)
Clarity: Can users read body text at 140% zoom?
Identity: Do returning visitors recognize the Art Deco aesthetic?
If texture feels essential after deployment, add minimal SVG accents or one background gradient. Iterate. Don't overbuild upfront.

Conclusion
Mockups sell the dream. Production honors the mission.

Our mission: engineered worlds, lasting experiences.

Texture serves that goal only if it doesn't compromise it. Sometimes restraint is the most Art Deco choice of all.
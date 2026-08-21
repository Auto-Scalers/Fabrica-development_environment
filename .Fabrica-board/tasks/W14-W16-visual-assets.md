# W14+W15+W16: Update landing page visual assets in Fabrica-web

Read Fabrica-web/AGENTS.md for conventions first.

## W14 — Replace carousel images

The current ShowcaseCarousel.tsx (components/Blocks/ShowcaseCarousel.tsx) references old image paths that don't exist. Update them to match the actual files in public/images/carousel/:

Map the slides to matching images:
- slide-01 (autonomous engine) → /images/carousel/carousel-00-manual-work-vs-247-autonomy.jpg
- slide-02 (parallel crews) → /images/carousel/carousel-04-parallel-crews.jpg
- slide-03 (approval gates) → /images/carousel/carousel-07-visual-approval-gates.jpg
- slide-04 (knowledge channels) → /images/carousel/carousel-06-knowledge-vault-channels.jpg
- slide-05 (beyond code) → /images/carousel/carousel-03-beyond-code-operations.jpg

Also update en.json showcase.slides image paths to match.

CRITICAL: Images must show FULL pictures — no cropping. The current aspect ratio 16/9 to 21/9 crops vertically. Consider using object-contain or a taller aspect ratio so images show completely without being cut off.

## W15 — Add standalone images

Each of these 5 standalone images MUST appear in the landing page. Map them to their matching sections:

1. /images/standalones/pain-exhausted-developer-11pm.jpg → PainSection (the pain section)
2. /images/standalones/social-parallel-agents.png → TurnSection or CrewSection (parallel agents)
3. /images/standalones/social-approval-gate.png → ControlSection (approval gates)
4. /images/standalones/mobile-companion-remote.jpg → ControlSection or OrchestrationSection (mobile companion)
5. /images/standalones/hands-on-architecture.jpg → FeatureSection/WhyFabrica (architecture)

Add them as img elements in the relevant section components. Use object-contain to show FULL images. If a section is a Server Component, add 'use client' or handle the image appropriately.

## W16 — Apply fabrica-buttom-bg to bottom section

The FinalCta.tsx needs fabrica-buttom-bg.png as background, following the SAME pattern as the Hero section background.

Hero background pattern (from Hero.tsx lines 196-206):
```tsx
<div className="absolute inset-0 pointer-events-none"
  style={{
    backgroundImage: 'url(/images/fabrica-hero-bg.jpg)',
    backgroundSize: '100% auto',
    backgroundPosition: 'center 32px',
    backgroundRepeat: 'no-repeat',
    filter: 'blur(1px)',
  }}
/>
<div className="absolute inset-0 bg-white/20 dark:bg-[#0B0C12]/60 pointer-events-none" />
```

Apply the same pattern to FinalCta using /images/fabrica-buttom-bg.png instead.

## RULES:
- Do NOT edit .backup/ or _sources/
- Do NOT commit or push
- Do NOT add new dependencies
- After changes, verify with grep that old image paths are gone
- Verify all 5 standalone images are referenced in the code

# Abdulla Hammad / NAVRIXA

A cinematic portfolio built with React 19, Next.js-compatible App Router, TypeScript, Tailwind CSS, Lucide and accessible Radix primitives. The Sites preview uses Vinext; the same application runs with Next.js on Vercel. Subtle CSS and IntersectionObserver motion avoids an extra animation dependency and respects reduced-motion preferences.

## Run locally

Requires Node.js 22.13 or later.

```sh
npm ci
npx next dev
```

## GitHub and Vercel

Push this project to your own GitHub repository, then import that repository into Vercel. The checked-in `vercel.json` selects Next.js and `npx next build` instead of the Sites build. Set `NEXT_PUBLIC_SITE_URL` to your final HTTPS domain. Run `npx next build` locally to verify the Vercel target.

The Sites-specific tooling and `.openai` configuration support the private preview and do not need to be used on Vercel. Never commit `.env`, provider tokens or service secrets.

## Edit the portfolio

- `data/portfolio.ts`: projects, organisations, experience, education, skills, services, project types and social links.
- `components/portfolio/site.tsx`: named, reusable page sections and contact form.
- `app/globals.css`: visual tokens, responsive layouts and reduced-motion styles.
- `app/layout.tsx`: SEO, Open Graph, X metadata and Person/Organization structured data.
- `public/images`: supplied portraits and NAVRIXA branding converted to lightweight WebP.

Project cards currently describe practice areas supplied in the brief. Their photographs show Hammad at work and NAVRIXA branding; they are not claimed as client deliverable screenshots. Add actual project-specific thumbnails, approved work samples and video URLs as available. No video or third-party player loads automatically.

## Contact form

By default, the form validates the enquiry and prepares an email draft. It does not send or store submissions. The visitor must press Send in their email application. Set `NEXT_PUBLIC_CONTACT_ENDPOINT` to a Formspree-compatible JSON endpoint or your own API to enable direct delivery. Implement validation, spam protection and rate limiting in any custom server endpoint; keep email-provider secrets on the server. Non-2xx responses show an error with the direct email fallback.

Instagram handles are editable in the data file. GitHub and LinkedIn are intentionally unlinked until verified profile URLs are supplied. Unknown experience dates and education institutions are left unspecified. The experience statistics and qualifications reflect the owner's supplied brief.

## Media and accessibility

Next Image reserves dimensions, requests responsive sizes and lazy-loads below-fold media. Vercel serves image optimisation; source WebP images remain lightweight for alternate hosting. Hero imagery is prioritised. No large video downloads or autoplay. Navigation and project dialogs are keyboard accessible with focus management, labelled fields, a skip link and reduced-motion support. Inter uses Google Fonts with a system fallback.

## Video and photo galleries

`data/videos.json` contains all 97 public uploads returned by NAVRIXA's uploads playlist during this update, including Shorts. The gallery uses original titles and responsive YouTube thumbnails, with 12 cards per load and search across the full collection. Players load only when requested and stop when closed. The Play All Uploads player uses `UUsCb-Wi579AphcbgUtcmF_Q`; the playlist is maintained by YouTube. Individual embedding availability remains controlled by YouTube and the uploader. All player dialogs include a direct YouTube fallback.

To add future uploads to the card gallery, add their video ID, title and thumbnail URL to `data/videos.json`. The playlist player follows the channel's uploads independently of the local card snapshot.

`components/portfolio/media-gallery.tsx` contains the video and photo sections. The two selected Instagram images are local WebP copies from the owner's public posts `DcPztMXR_rZ` and `DcTV3jdpmKB`, each linked to its original post. Their exact appearance was inspected before selection. This is a curated selection, not an automated Instagram feed or a claim of engagement ranking.

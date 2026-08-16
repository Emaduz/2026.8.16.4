# Project TODO

- [x] Analyze emadalddine.com for current content structure, typography, colors, spacing, and responsive behavior
- [x] Preserve the current visual identity while improving hierarchy, polish, and responsive layout
- [x] Build public homepage with hero/profile, about/bio, portfolio/projects, blog/posts, cover images, contact, and social sections
- [x] Add database schema for editable static sections, projects, posts, and cover image metadata
- [x] Add public procedures for published posts, published projects, and editable site sections
- [x] Add owner-only admin authorization using the existing authenticated owner role
- [x] Build admin dashboard using the provided DashboardLayout component
- [x] Add project CRUD with title, description, cover image, and publish/draft toggle
- [x] Add post CRUD with title, summary, body, date, cover image, and publish/draft toggle
- [x] Add static section editor for bio/about and contact/social links
- [x] Add secure image upload flow using S3-backed file storage
- [x] Register public and admin routes with responsive navigation and clear escape routes
- [x] Add Vitest coverage for content authorization and CRUD/public publishing behavior
- [x] Run typecheck, tests, and visual responsive verification
- [x] Create final checkpoint after all TODO items are complete
- [x] Deliver the checkpoint version to the user

## Change history

- [x] New scope: full public personal site plus owner-only admin control panel with live publishing
- [x] New constraint: mirror emadalddine.com content structure, fonts, colors, and overall visual identity
- [x] New requirement: mobile and desktop responsive behavior
- [x] New requirement: image upload support for post/project cover images
- [x] New requirement: published content updates public site immediately
- [x] New requirement: strict owner-only admin access

## Implementation note

The initialized project already includes Manus OAuth, database access, S3 storage helpers, and a reusable DashboardLayout. The admin area will use authenticated owner/admin authorization rather than exposing an unprotected password field in the client.

## Open validation

- [x] Confirm whether the existing site content is expected to be imported verbatim or whether the admin panel should start with editable empty fields where content is unavailable — existing homepage copy and project images were seeded; no articles were invented, so the posts list starts empty
- [x] Confirm exact admin login preference if a separate password is required in addition to Manus owner authentication — implemented as owner authentication plus a separate server-side admin password gate

## Follow-up requirements before final checkpoint

- [x] Add an editable publishedAt date field to posts, its schema, admin form, public rendering, and mutations
- [x] Add Vitest coverage for create/update/delete/toggle flows and public published-only filtering
- [x] Add a separate owner password gate in addition to the existing owner authentication, configured through ADMIN_PANEL_PASSWORD

## Password-session hardening

- [x] Read the admin access cookie from the request Cookie header so it works across real requests and reloads
- [x] Add an integration-style test covering verify password, set cookie, and protected content access

## Password session persistence

- [x] Use a password-derived access token instead of a plain cookie value
- [x] Add a lightweight password-session status procedure and restore the admin UI state after reload
- [x] Add test coverage for token-backed status and reload-style protected access

## Navigation and interaction update

- [x] Make top navigation tabs open dedicated pages for Home, Portfolio, About, Services, Contact, and Admin
- [x] Build a dedicated portfolio page with every project presented in an interactive carousel
- [x] Add dedicated About, Services, and Contact page layouts that reuse the current visual identity and editable content
- [x] Add smooth page transitions and active-tab states
- [x] Add deliberate mouse-wheel/scroll effects with reduced-motion support and mobile-safe behavior
- [x] Add route and carousel interaction tests plus responsive visual verification

## Final interaction hardening

- [x] Back the Services page cards and copy with admin-managed site content, using safe fallback values
- [x] Add executable interaction coverage for route rendering and carousel next/previous/scroll behavior, and ensure it runs in pnpm test

## Final validation gaps

- [x] Bind Services page headings, intro, and process copy to admin-managed site content with fallbacks
- [x] Add jsdom-based rendered interaction tests for route/page output and carousel controls plus wheel behavior

## Router and carousel coverage completion

- [x] Add a jsdom test around the actual public App router that verifies distinct page output and tab navigation
- [x] Extend rendered carousel coverage to include previous/back control behavior as well as next and wheel behavior

## User-requested visual and content update

- [x] Apply Georgia 400 italic to display headings, with white or warm pink accent colors matching the reference
- [x] Make the Arabic language button switch the public site into Arabic RTL mode and back to English
- [x] Show the Control link in the public top navigation consistently, including responsive navigation
- [x] Rebuild the About profile visual using the same circular portrait composition as the Home hero
- [x] Change Portfolio from one slide per project to nested project carousels with explanation, applications, mockups, and project stages
- [x] Prepare Behance project import/source mapping for emadalddine.net/projects while keeping the public UI free of Behance branding — source metadata and selected actual Behance modules are stored locally
- [x] Expand the 4K desktop layout to use more viewport width, reduce excessive side margins, and improve text legibility
- [x] Support right-to-left data presentation when Arabic mode is active
- [x] Add tests for language switching, navigation visibility, nested portfolio carousel behavior, and 4K/RTL layout contracts
- [x] Run typecheck, tests, build, and desktop/mobile/4K visual verification
- [x] Save a new checkpoint for this update
- [x] Deliver the updated checkpoint to the user

## Remaining portfolio import gaps

- [x] Seed/import multiple internal carousel slides for every published portfolio project so none relies on a single fallback slide
- [x] Complete local Behance project-page mapping for every displayed project and verify the public carousel renders without external Behance image dependencies

## Behance fidelity hardening

- [x] Import/store the actual internal page or module content for each displayed Behance project instead of generic local placeholder descriptions
- [x] Add a verification test asserting every published portfolio project has multiple slides and every public slide image uses a local /manus-storage path

## Isti motion & alignment update

- [x] Refine typography hierarchy, heading scale, and left/right alignment across all public pages
- [x] Implement scroll reveal, staggered entrances, and smooth page transitions inspired by Isti without adopting its dark/lime color scheme
- [x] Add a floating WhatsApp icon linked to the site's contact phone number with hover and mobile affordances
- [x] Run typecheck, tests, build, and responsive visual verification
- [x] Save checkpoint and deliver the update

## Comprehensive User Feedback Update (Phase 2)

- [x] Unify portrait styling with circular orbits and badges across all pages
- [x] Replace project carousel with a card-grid layout in Portfolio and build dedicated project detail pages (/portfolio/:id)
- [x] Seed the 8 requested Behance projects in the exact user-specified order with rich local slides
- [x] Make the top navigation bar fixed during mouse scroll
- [x] Redesign language switch button and add a Light/Dark theme toggle button beside it
- [x] Replace fonts strictly with Google Rubik variable font (supporting Arabic and English)
- [x] Implement robust Arabic translation dictionaries for all public sections and dynamic content fallback
- [x] Widen desktop and mobile side margins/paddings for a spacious, legible reading experience
- [x] Add smooth scroll motion and card-hover motion to the "Crafted for clarity" services section
- [x] Remove Control tab from top navigation and rename admin route to /Emadalddine
- [x] Build a simplified admin login screen supporting username/password with "Forgot password" (email: Emad.i202020@gmail.com) and WhatsApp recovery (+966504487308)
- [x] Run typecheck, vitest tests, build, and responsive visual verification
- [x] Save final checkpoint and deliver

## Final Technical Feedback Update (Apple style & spacing)

- [x] Refine heading scales and typography to match clean, balanced Apple typographic hierarchy
- [x] Increase line-height and paragraph spacing to prevent text crowding
- [x] Improve text contrast on dark background sections with lighter brand-aligned tones
- [x] Enlarge the personal portrait composition in the Home hero section
- [x] Redesign project detail pages (/portfolio/:id) with an Apple-inspired horizontal/carousel card-grid layout showing peek-next preview cards
- [x] Run typecheck, vitest tests, build, and responsive visual verification
- [x] Save final checkpoint and deliver

## Admin Session & Draft Autosave Fixes
- [x] Implement robust admin session persistence with an extended timeout and pre-expiration warning banner
- [x] Add automatic draft autosave to localStorage during project/post creation and editing
- [x] Implement one-click draft recovery after accidental browser closure or network interruption
- [x] Verify session persistence across tab switches and test draft restoration flow
- [x] Run typecheck, vitest tests, build, and save final checkpoint

## Final User Feedback — Portrait, Localization & Control Panel
- [x] Remove the portrait background frame and keep the circular portrait with galaxy-like orbit lines only
- [x] Add small continuously orbiting decorative spheres using the brand palette, with reduced-motion support
- [x] Add practical portrait anti-download protections: no direct link, no dragging, and no context menu
- [x] Reorder About: portrait beside the headline, quick-note CTA in a separate lower section, and contact split left/right
- [x] Keep the WhatsApp CTA visible by default inside the quick-note card
- [x] Add a persistent active-tab highlighter in the top navigation
- [x] Hide the Emadalddine control-panel entry from the public footer
- [x] Add bilingual Arabic and English editing fields to the admin content forms and persist both variants
- [x] Add separate cover-image fields for projects and posts, independent from project-stage images
- [x] Add tests for bilingual admin content, cover images, active navigation, portrait motion, and public privacy affordances
- [x] Run typecheck, Vitest, build, responsive verification, and save a final checkpoint

## User Feedback — Portrait Box & Proportions (Pending Start)
- [x] Remove the outer bounding card/box around the About portrait composition entirely.
- [x] Enlarge the central portrait to ~70% of the composition area and scale down the galaxy orbit lines and planets to ~30% compactness around it.
- [x] Update Services with the complete 8 categories and bilingual translations.
- [x] Add the continuous Marquee Client Feedback section before the journal section.
- [x] Overhaul the Homepage Hero layout to match the Ethan-style reference (top headline, right-side contacts, portrait visual with 70% size, 30% compact orbits, and specialization badges).

## Additional User Feedback — Hero Colors, Portrait Proportions & CV Upload
- [x] Align hero background and visual style strictly with the site's original brand identity colors instead of bright lime green.
- [x] Enlarge the central portrait image properly while keeping the galaxy orbits and moving planets at a fixed compact scale.
- [x] Remove the thick white circle ring around the portrait composition.
- [x] Add a dedicated CV/resume PDF upload field in the admin panel to allow managing and updating the downloadable CV file.
- [x] Connect the "Download CV" button on the public homepage to the uploaded resume PDF URL.
- [x] Add sufficient top spacing below the fixed header so hero title and contact information never sit underneath the navigation bar, including RTL and mobile layouts.

## User Feedback — Remove Hero Visual Box & Badges
- [x] Remove the outer rounded background card/box behind the portrait composition in the homepage hero.
- [x] Remove all three specialization badges (Branding & Market Research, UI/UX Designer, Graphic Designer) marked with an X.
- [x] Keep only the central portrait composition, galaxy orbits, and moving planets on a clean transparent background.

## User Feedback — Remove Bottom Gap/White Crescent in Portrait
- [x] Remove the bottom white gap / crescent shadow beneath the portrait image across all pages.
- [x] Adjust image scaling and vertical offset (`object-position` or `translateY`) so the circular crop fills the entire container seamlessly without any bottom gap.

## User Feedback — Behance Official Icon & Portrait Bottom Gap
- [x] Replace the checkmark icon for Behance with the proper official Behance SVG mark (`Be`) across all social links and footer/contact sections.
- [x] Adjust image cropping/scaling and container overflow to eliminate any white bottom crescent or gap inside the circular portrait.

## User Feedback — Orbit-only refinement
- [x] Preserve the current image, colors, background, typography, spacing, section order, and all existing page elements without unrelated redesign.
- [x] Use exactly three separate soft elliptical orbit paths at slightly different angles around the current image.
- [x] Add one small moving asteroid/dot to each orbit with calm, continuous motion and distinct speed/direction.
- [x] Keep orbit colors limited to the existing brand palette, keep the portrait unobstructed, and support responsive sizing and reduced motion.

## User Feedback — Replace portrait source
- [x] Replace the current portrait source with the user-provided image while preserving the existing Orbit-only treatment and all other page styling.

## User Feedback — About reference page
- [x] Rebuild About page structure to match the user-provided emadalddine.com About reference: centered intro, portrait/sidebar information, languages, story, experience timeline, and skills.
- [x] Keep the About reference layout bilingual and responsive without changing other public pages.

## User Feedback — Portrait zoom out
- [x] Zoom the current portrait out inside its circular frame so both shoulders are visibly included while keeping Orbit paths and planets unchanged.

## User Feedback — Portrait top breathing room
- [x] Add visible top breathing room inside the circular portrait so the hair never touches or gets clipped by the frame, while preserving shoulder visibility and the existing Orbit paths.

## User Feedback — Match Contact reference page
- [x] Rebuild the public Contact page to match the user-provided emadalddine.com contact reference while preserving bilingual content, current brand identity, and responsive behavior.

## User Feedback — Match Services reference page & Admin Control
- [x] Rebuild the public Services page to match emadalddine.com reference layout and make all services content fully editable from the admin panel in both Arabic and English.

## User Feedback Batch 2 — Pending Implementation
- [x] Hero adjustments: shrink portrait slightly inside, align heading horizontally with the portrait on the left, remove floating contact card, and format phone number with country code on the left (LTR numeric flow).
- [x] About section (Little About Me): replace portrait with the logo graphic, remove outer square frame and orbit/motion lines.
- [x] Pure Arabic localization: refine all Arabic copy across all pages to sound natural and purely Arabic.
- [x] Featured Work section: adopt the reference layout style (large feature card on the right, stacked project cards on the left) maintaining site brand colors and Rubik typography.
- [x] Services section: display at least 8 services in an Apple Watch-style circular/grid constellation layout using brand identity and typography.
- [x] About page: make the profile portrait static without animation/orbits inside the contact card area.

- [x] Featured Work drag-to-scroll carousel supporting mouse drag and touch gestures as shown in the reference video.

- [x] Remove background constellation circles/orbits from the Services section and convert the 8 services into a continuous horizontal marquee ticker supporting drag-to-scroll and touch interaction.

- [x] Reverse the Services marquee ticker animation direction from right-to-left to left-to-right.

- [x] Redesign the "Ready to Get Started" CTA section in the Services page with proper side alignment, balanced spacing, and a modern custom layout.

- [x] Replace the profile portrait with the site logo graphic inside the profile card on the Contact page.

- [x] Replace the profile portrait source globally across all components (Hero, About, etc.) with the newly attached portrait image while keeping all framing, orbits, and styling intact.

- [x] Adjust portrait image fit/zoom (`object-fit: contain` or adjusted scaling) so all edges fit entirely inside the circular frame across all instances.
- [x] Add an admin control panel section and backend procedure for uploading and updating the owner profile portrait.

- [x] Make internal page navigation start at scroll top while browser Back restores the previous page scroll position.

- [x] Connect each design package card in the Services page to direct WhatsApp consultation opening with a pre-filled descriptive message in Arabic or English.

## Expanded Per-Page Layout and Element Editor

- [x] Build a comprehensive page layout settings model for element positioning, div alignment, icon style selection, section reordering, spacing, and sizing
- [x] Upgrade PageEditorView to support detailed element controls per page without breaking existing defaults
- [x] Apply layout and positioning variables dynamically to public pages
- [x] Run typecheck, unit tests, and production build verification
- [x] Save checkpoint and deliver the expanded editor

## Vercel Deployment & Pnpm Build Scripts Fix

- [x] Add pnpm.neverBuiltDependencies or pnpm.onlyBuiltDependencies configuration in package.json or .npmrc to approve @tailwindcss/oxide and esbuild build scripts
- [x] Verify local build success with approved dependency build scripts
- [x] Save checkpoint and provide Vercel redeployment guide

## Self-Contained ZIP Export & Asset Portability

- [x] Ensure all local portrait and branding assets are included in public directory or portable S3 fallback URLs for Vercel/GitHub deployment
- [x] Create a clean distribution ZIP archive of the current project root
- [x] Provide clear import مستدامة للرفع على GitHub و Vercel

## Vercel Serverless & Bundle Fixes

- [x] Add vercel.json configuration to map Express server build correctly for Vercel serverless functions
- [x] Ensure package.json build script and start scripts are Vercel-compatible
- [x] Rebuild and package clean ZIP for Vercel deployment

## External MySQL Database Setup for Vercel

- [x] Choose a free MySQL or TiDB cloud database provider (e.g. PlanetScale, Aiven, or Railway)
- [x] Obtain the DATABASE_URL connection string
- [x] Push database migration schema using drizzle-kit migrate or SQL script
- [x] Configure DATABASE_URL in Vercel Environment Variables and redeploy

## Vercel Pnpm Lockfile & Config Fixes

- [ ] Remove deprecated patchedDependencies property from package.json to match pnpm settings
- [ ] Regenerate clean pnpm-lock.yaml compatible with Vercel pnpm install
- [ ] Update vercel.json to use standard npm/pnpm install command without frozen lockfile mismatch

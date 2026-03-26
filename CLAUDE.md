# MZ's 40th Birthday Trip Website

## Project Overview

A single-page collaborative website for planning MZ's 40th birthday trip: a long weekend at a villa in Mezy-sur-Seine, France (Fri 1 May - Mon 4 May 2026). The group is 7 adults and 1 toddler (age 3).

## Tech Stack

- **Single HTML file** (`dashboard.html`) — all HTML, CSS, and JavaScript in one file
- No build tools, frameworks, or bundlers
- **Firebase** for backend persistence (Firestore for shared state, synced across all users in real-time)
- Hosted as a static site (GitHub Pages or similar)

## Architecture

The site is organized as a tabbed dashboard with these sections:

- **Overview** — guest list, villa details, nearby attractions
- **Itinerary** — day-by-day schedule (Fri-Mon) with timeline items tagged as Everyone/Adults/Kid-friendly
- **Vote** — activity voting system (one vote per person per activity, with suggestions)
- **Who's Bringing What** — item claim list organized by category (BBQ, Drinks, Breakfast, Birthday Bits, Gear, Other) plus dietary requirements
- **Message Wall** — "40 messages for 40 years" goal, user-submitted messages
- **Travel Info** — driving directions, villa address, key reminders, weather
- **Packing** — checklist with checkable items

All interactive state (votes, claims, messages, checklist) is persisted in Firebase and synced in real-time across users. Users select their name via a name-picker pattern before interacting.

## Key Details

- **Villa**: Mezy-sur-Seine, Yvelines 78250, France (Airbnb)
- **Travel**: Folkestone Le Shuttle to Calais, then ~3h drive south
- **Guests**: MZ (birthday), Wife, Son (3yo), Brother, Sister, Cousin, plus others (7 adults total)
- **Design**: Dark theme with gold (#c9a84c) and accent red (#e94560), Playfair Display headings, Inter body text

## Conventions

- Keep everything in the single `dashboard.html` file unless there's a strong reason to split
- Maintain the existing CSS variable system (defined in `:root`)
- Mobile-responsive — test at 600px breakpoint
- Use the existing name-picker pattern for any new interactive features
- Tags for itinerary items: `tag-all` (Everyone), `tag-adults` (Adults), `tag-kid` (Kid-friendly)
- No external JS dependencies beyond Firebase — vanilla JavaScript otherwise

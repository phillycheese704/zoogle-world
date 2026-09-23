🥚🌍 Zoogle World 🌍🥚

Zoogle World is a single-file browser creature-collection and idle game built with HTML, CSS and JavaScript.

Hatch eggs, collect Zoogles, place them on floating islands, earn coins and gems, breed new creatures, discover mutations, complete quests, survive changing weather, visit other worlds, and play shared multiplayer sessions.

Current release

Pass & Polish V1 is the current stabilization release. The visible in-game title remains 🥚🌍 ZOOGLE WORLD 🌍🥚.

This release focuses on reliability, multiplayer usability, responsive layouts and quality-of-life rather than another large content drop. It also includes the Aliens Invade V1 content: the Moon, Space Merchant, Mothership, Alien/Lunar eggs, alien Zoogles and Abduction weather/mutation content.

Features

Egg Market and multi-slot Hatchery

Distinct egg artwork across the progression tiers, including Alien and Lunar eggs

Main Island, Rocky Island, Storage Cliffs, Tribal Island, Breeding Cave, Mutation Lab, Moon and Mothership

100+ collectible Zoogles across Common, Uncommon, Rare, Epic, Legendary, Celestial and Ancient rarities

Breeding recipes plus rarity-based fallback breeding

Mutation system, weather mutations and Mutation Lab experiments

Dynamic weather including Rain, Snow, Heatwave, Volcano, Starfall, Aurora and Abduction

Coin and gem generation, selling, mastery and storage

Upgrade system with area-specific capacity modules

Daily, progression and special quests

Zoogle Index with search, sorting and filters

Space Merchant with rotating shared stock

Island Passport, likes, visits and world viewing

Realtime shared multiplayer using Supabase

Area music, sound effects and weather ambience

Mouse, touch, responsive mobile/tablet UI and gamepad support

Reduced Motion and UI scaling options

Play / deploy

There is no build step. The playable game is simply:

index.html

**or**

https://phillycheese704.github.io/zoogle-world/
For GitHub Pages, place index.html in the repository root and enable GitHub Pages for that branch/folder.

The game remains a static GitHub Pages site. Supabase is used only for cloud/world-sharing/multiplayer services.

Supabase setup

The browser must only contain the public/publishable Supabase key. Never put a service_role key, secret server key or database password in index.html or the repository.

For a fresh Aliens Invade deployment, run the Aliens V1 migration in the Supabase SQL Editor before deploying the matching HTML. If the multiplayer stability/reseed patch has not already been installed, also run:

zoogle_world_multiplayer_stability_fix.sql

That patch is safe to rerun and does not delete Passport worlds, likes, visits or local saves.

Multiplayer behaviour

Multiplayer is offline by default. Loading your home world does not automatically start a live shared-world session.

Players can still view worlds and send join requests while the host is offline. The host becomes live only after accepting a join request. Reloading the game returns the host to the normal offline home world.

While live, shared state includes currencies, Zoogles, eggs, Hatchery progress, breeding, upgrades, quests, weather, merchant state and other durable world data. Presence and cursors use Supabase Realtime.

The multiplayer backend is designed for cooperative play with friends/family. It is not intended to be a hardened anti-cheat service for hostile public players.

Pass & Polish V1 stability work

This release includes several defensive changes intended to make future updates harder to break:

authoritative area ordering and area-name repair

recovery when a renderer throws instead of leaving the game blank

fixed Moon/Mothership renderer scoping that could previously break island navigation

Breeding Cave and Mutation Lab rendering guards

special-area save recovery, including reloading from Mutation Lab

stale breeding-parent cleanup

lower-frequency multiplayer background simulation to reduce action contention

clearer Hatchery capacity (N / MAX) and full-state feedback

disabled purchase/upgrade buttons now explain insufficient currency or full capacity

Escape closes normal modals/action panels

additional small-screen Cave/Lab/Market layout hardening

no duplicate static DOM IDs in the release build

a developer health check for future debugging

To run the health check in the browser console:

ZoogleHealthCheck()

It reports the current area, area order, duplicate IDs/areas, invalid egg/Zoogle references and basic multiplayer state without modifying the save.

Local development

From the folder containing index.html, run:

python -m http.server 8000

On Windows this may also be:

py -m http.server 8000

Then open:

http://localhost:8000

Keep the terminal open while testing.

Controls

Mouse / touch

Use the on-screen controls to navigate areas, open menus, hatch eggs, place Zoogles and interact with game systems.

Controller

The game uses the browser Gamepad API for navigation and common actions. Core mappings include directional navigation, confirm/back, Collect All, Index, Market and island switching.

Saves

Single-player progress is stored locally in the browser. Online features also store world/passport/multiplayer data in Supabase.

The current migration layer preserves older saves, moved upgrade levels and legacy Nature Eggs. Avoid clearing browser storage or using Reset Save unless you intentionally want to start over.

Before major releases, keep a known-good copy of the previous index.html.

Project structure

/
├── index.html
├── README.md
└── *.sql        # Supabase migrations / patches when required

Most game code, CSS, animations and visual assets live directly inside index.html.

Release testing

Pass & Polish V1 has been syntax-checked across all inline JavaScript blocks and smoke-tested in a headless Chromium run across these viewport sizes:

320×568
375×812
430×932
768×1024
1366×768
1920×1080

The automated smoke test cycled through all eight areas and verified their displayed names and primary scene visibility, plus basic offline egg purchasing and modal closing.

Live Supabase multiplayer still needs real multi-device testing against the deployed project; automated local tests cannot reproduce network latency, disconnects and two-player race conditions perfectly.

Development status

Zoogle World is actively developed. The current priority is keeping the now-large single-file game stable while continuing to add polish and carefully tested content.

Made for the joy of collecting increasingly strange little Zoogles. 🥚👽

# 🥚🌍 Zoogle World 🌍🥚

**Zoogle World** is a single-file browser creature-collection and idle game built with HTML, CSS and JavaScript.

Hatch eggs, collect and place Zoogles, earn coins and gems, unlock new areas, breed creatures, discover mutations, complete quests, survive changing weather, and visit other players' worlds.

## 🎮 Features

- 🥚 Egg shop and Hatchery
- 🌍 Multiple unlockable islands and areas
- 🧬 Mutation system and Mutation Lab
- 💕 Breeding Cave with breeding recipes
- 💰 Coin and gem generation
- ⬆️ Upgrade system
- 🌦️ Dynamic weather and weather mutations
- 📖 Zoogle collection/index with search and filters
- ✅ Daily, progression and special quests
- 📦 Storage systems
- 🗿 Tribal and Ancient content
- 🌐 Island Passport and island sharing
- 👥 Realtime multiplayer using Supabase
- 🎵 Area music and sound effects
- 📱 Responsive phone and tablet controls
- 🎮 Gamepad/controller support
- ♿ Reduced Motion and UI scaling options

## 🚀 Play

The game has no build step. The playable game is simply:

```text
index.html
```

the link is; https://phillycheese704.github.io/zoogle-world/

## 💻 Run locally

From the folder containing `index.html`, run:

```bash
python -m http.server 8000
```

On Windows, this may also work:

```bash
py -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Keep the terminal window open while playing.

## 🌐 Multiplayer

Zoogle World itself stays hosted as a static GitHub Pages site.

Supabase is used for online features such as:

- anonymous player authentication
- Island Passport sharing
- join requests
- realtime presence and player cursors
- shared multiplayer state
- multiplayer locks and synchronization

The game should only use browser-safe/public Supabase credentials in `index.html`. Never put a Supabase `service_role` key or other private server secret in the repository.

Some game versions may include accompanying `.sql` migration files. Run required migrations in the Supabase SQL Editor before testing features that depend on them.

## 📱 Controls

### Mouse / touch

Use the on-screen controls to navigate islands, open menus, hatch eggs, place Zoogles and interact with game systems.

### Controller

The game includes Gamepad API support for navigation and common actions. Exact mappings are surfaced by the in-game UI/settings where available.

## 💾 Saves

Single-player progress is stored locally in the browser.

Multiplayer/world-sharing features also use Supabase. Avoid clearing browser storage or resetting the save unless you intend to start over.

## 🛠️ Project structure

The game is intentionally kept simple:

```text
/
├── index.html
├── README.md
└── *.sql        # Supabase migrations when needed
```

Most game code, styling, animations and assets are contained directly inside `index.html`.

## 👽 Upcoming

The next major expansion is currently planned as:

**Zoogle World — The Aliens Invade**

Planned ideas include new islands, new eggs and Zoogles, alien weather and mutations, a Space Merchant, a Mothership upgrade console, multiplayer stabilization, and a wider responsive-UI overhaul.

## ⚠️ Development status

Zoogle World is actively being developed. Multiplayer and new gameplay systems may change between versions, so keep backups of known-good `index.html` files before major updates.

---

Made for the joy of collecting increasingly strange little Zoogles. 🥚

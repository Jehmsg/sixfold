# Sixfold

**Six guardians. Five encounters. One crown to break.**

Sixfold is a browser-based, keyboard-and-mouse raid shooter — a co-op, loot-driven FPS in the
spirit of raid-based shooters, built as a single self-contained HTML file (Three.js r128, no build
step).

## Play

Open `index.html` in a desktop browser (Chrome, Edge, or Firefox — any modern WebGL browser).
No install, no build, no server required for single player. Progress saves automatically to your
browser's `localStorage`.

## Classes

| Class | Role | Signature jump | Ability (C) | Super (F) |
|---|---|---|---|---|
| **Bulwark** | Front-line defender | Lift — powerful second jump | Ward — dome that halves ally damage | Earthbreaker — leap-slam that flattens nearby enemies |
| **Strider** | Agile marksman | Triple jump — two extra air jumps | Evade — dash + instant reload | Gilded Volley — three solar shots that delete one target |
| **Arcanist** | Space-magic support | Glide — hold jump to drift | Rift — well of light that heals allies | Starfall Nova — collapsing star that detonates on impact |

## Raids

- **The Hollow Crown** (Light 36) — a sunken citadel where a dead king still sits his throne.
  Sundered Gate → Pillars of the Fall → the Ashen Oracle → the Twin Wardens → Aurex, the Hollow King.
- **Vault of the Drowned Star** (Light 50) — beneath a black sea, a fallen star still burns.
  The Tidegate → Choir of the Deep → the Sunken Stair → the Abyssal Pair → Thal'veth, Heart of the Deep.
- **The Ashen Expanse** (endless patrol) — endless enemies, frequent engrams, a champion every couple
  of minutes.

Encounter types: **breach** (charge a gate while gatekeepers hold it), **ascent** (a generated climb
of the fallen spire), **lantern** (solo boss), **twins** (dual bosses), **king** (final boss).

## Loot & gear

- 9 weapon archetypes across primary / special / heavy slots (auto, pulse, hand cannon, scout,
  shotgun, sniper, fusion, machine gun, rocket launcher).
- 5 rarities: Common → Uncommon → Rare → Legendary → Exotic, with per-raid item power ranges.
- Weapon perks (Deep Magazine, Rampage, Final Round, …), exotic weapons with unique perks, and
  exotic armour with class-tuned perks.
- Raid set bonuses: 3 pieces = +10% damage in that raid, 5 pieces = +20% damage and +25 shield.
- Engrams (raid engrams roll raid-tier gear), and a **Light** power score per guardian.
- Cosmetics: armour finishes, helmet ornaments, back/aura attachments, weapon skins, body build,
  skin/armour/trim/visor colours.

## Controls

| Key | Action |
|---|---|
| `WASD` | Move — hold `Shift` to sprint |
| `Space` | Jump, then class jump in mid-air (Arcanist: hold to glide) |
| Mouse | Left: fire · Right: aim down sights |
| `1` `2` `3` / wheel | Primary / special / heavy weapon |
| `R` | Reload |
| `G` | Grenade |
| `V` | Melee |
| `C` | Class ability |
| `F` | Super |
| `E` | Interact — pick up / drop relics |
| `Esc` | Pause |

## Multiplayer (fireteam co-op)

Up to six guardians can raid together: the fireteam leader's game runs the encounter and everyone
else joins it live (host-authoritative — the host streams a compact game snapshot; clients stream
their position and report their hits). Loot is personal: every guardian rolls their own chests.
The hub's **Fireteam** tab can create a team, share its code, or join a listed open team. AI
guardians fill empty fireteam slots in solo play.

> **Note on where this runs:** the co-op and cloud-save features are wired to the Claude hosting
> runtime (`window.claude` room/DB services) that the game was originally built in. Outside that
> runtime the game fully works as single player with local (browser) saves, and co-op gracefully
> switches off. A local-network server version is planned — see the roadmap below.

## Roadmap

- [ ] Local (LAN) host-and-join multiplayer: a small Node/WebSocket server replacing the Claude
      runtime room API, so a fireteam can be hosted from any machine on a home/office network.
- [ ] File-split the single HTML into modules (data / net / world / UI) for easier development.
- [ ] Vendor Three.js locally (no CDN dependency) for fully offline play.

## Repo layout

- `index.html` — the entire game: markup, styles, data tables, world, netcode, and UI in one file.

Built with Claude.

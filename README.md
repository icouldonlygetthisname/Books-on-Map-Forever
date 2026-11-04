<p align="center">
  <img src="Books_on_map_Forever/adds/Book_on_map_forever.png" alt="Books on map Forever" width="256">
</p>

# Books on map (Forever)

A World of Warcraft addon for **WoW Forever** that shows every library book on your world map and minimap. It ticks books off automatically as you find them, plans the shortest route through the ones you still need, and tracks your progress toward the library rewards.

- **Author:** Daeler (upstream: [EfkaBz/Books-on-Map-Forever](https://github.com/EfkaBz/Books-on-Map-Forever))
- **Version:** 2.1.0
- **Game versions (`## Interface`):** 11508, 11509, 11601, 16001
- **Languages:** English, French

---

## Contents

- [Features](#features)
- [Installation](#installation)
- [Getting started](#getting-started)
- [The book list window](#the-book-list-window)
- [Map and minimap icons](#map-and-minimap-icons)
- [Optimized route](#optimized-route)
- [Group mode](#group-mode)
- [Library rewards](#library-rewards)
- [Slash commands](#slash-commands)
- [Book list](#book-list)
- [Optional addons](#optional-addons)
- [Saved data](#saved-data)
- [Troubleshooting](#troubleshooting)
- [About this fork](#about-this-fork)
- [Credits](#credits)

---

## Features

- **Map and minimap icons:** every book you still need shows up on the zone map, the continent map and the minimap, each with its exact spot and coordinates.
- **Automatic detection:** a book is marked as collected when it lands in your bags or when you hand it in at the library. Books you handed in before installing the addon are picked up at login.
- **Item tooltips:** hovering over a library book anywhere shows *Library book – collected / missing* and which set it belongs to.
- **Optimized route:** the shortest path through your missing books, starting from where you stand. It comes with an on-screen tracker (arrow and distance), a dotted trail on the map, and optional TomTom waypoints.
- **Nearest book:** `/bom next` finds the closest book you still need.
- **Group mode:** party and raid members running the addon share their progress, so you can see which books they still need and help them collect.
- **Reward tracking:** a progress bar and a rewards tab for the 10, 20 and 25 book milestones.
- **Collection alerts:** a toast pops up for every book found, and a bigger one with a sound when you reach a reward milestone.
- **Chat sharing:** post your progress, and optionally the books you're missing, to your group, guild or say.
- **Minimap button and DataBroker:** works with Titan Panel, ChocolateBar, ElvUI, Bazooka, and minimap button collectors.
- **Faction aware:** books only the other faction can loot are removed from your list.

---

## Installation

1. Download the repository (green **Code** button → **Download ZIP**) or clone it.
2. Copy the **`Books_on_map_Forever`** folder (the one containing `Books_on_map_Forever.toc`) into your game's AddOns folder:

   ```
   <WoW Forever install>\Interface\AddOns\Books_on_map_Forever\
   ```

   The folder must be named exactly `Books_on_map_Forever`, because the addon loads its icons from that path. Don't copy the outer repository folder, the `.git` folder or this README.

3. Restart the game, or type `/reload` if it is already running.
4. On the character select screen, open **AddOns** and make sure **Books on map (Forever)** is ticked. If it shows as *out of date*, tick **Load out of date AddOns**.

### Updating

Delete the old `Books_on_map_Forever` folder and copy in the new one. Your collected books and settings are stored in `WTF` (see [Saved data](#saved-data)), so they are kept.

---

## Getting started

- A **welcome page** opens the first time you log in on your account. It lists the features and main commands, and lets you pick the language. Type `/bom welcome` to open it again.
- Open the **world map**: every book you still need appears as its book icon.
- Type **`/bom`**, or left-click the minimap button, to open the book list.
- Go and pick up books. Each one is checked off as soon as it's in your bags.
- When you reach 10, 20 or 25 books, hand them in at the library to claim your reward.

---

## The book list window

Open it with `/bom`, `/books`, the minimap button or a DataBroker display. Drag it by its title bar and close it with **Esc**.

**Title bar**

- **Bug**: shows the developer's Discord invite, selected and ready to copy with Ctrl+C.
- **Auto / EN / FR**: interface language. *Auto* follows your game client. Changing it reloads the UI, because book names are translated at load.

**Progress**

A bar from 0 to 25 books with markers at the necklace (10) and ring (20) goals. Each goal turns green once reached.

**Settings** (click the header to fold the section)

| Option | What it does |
|---|---|
| Show on the map | Show or hide all book icons on the world map |
| Map icon size | 10–40 (default 20) |
| Show books on the minimap | Show or hide book icons on the minimap |
| Minimap icon size | 8–30 (default 14) |
| Show the minimap button | Show or hide the minimap button |
| Notify when a book is collected | Turn the collection toasts on or off |

**Filters** (foldable)

| Filter | What it does |
|---|---|
| Hide collected books | Only list books you still need |
| Only sets for my level | Hide sets above your character's level (35 / 45 / 60) |
| Also show the books my group is missing | Show greyed icons for books a group member still needs, even if you have them |

**Book list**

Books are grouped by set (*Starting set*, *Level 35*, *Level 45*, *Level 60*), each with its own collected count. Click a set header to fold it.

- **Click** a book to open the world map on its zone.
- **Right-click** a book to set a TomTom waypoint (if TomTom is installed).
- **Tick the checkbox** to mark a book as collected by hand, or untick it to show the book on the map again.
- Hover over a book to see every location it can be found at, plus your group's status for it.

**Footer**

- **Show all**: marks every book as *not collected*, so all books return to the map.
- **Hide all**: marks every book as *collected*.
- **Optimized route**: turns the route tracker on or off.

**Side tabs**

- **Rewards**: the reward items for each milestone (see [Library rewards](#library-rewards)).
- **Group**: an icon grid of every group member's books (see [Group mode](#group-mode)).

---

## Map and minimap icons

**World map**

- Icons show on the book's zone map and, slightly smaller, on the Kalimdor and Eastern Kingdoms continent maps.
- **Hover** to see the book name, location, coordinates, route step, overall progress and your group's status.
- **Shift-click** to mark the book as collected.
- **Right-click** to set a TomTom waypoint.
- Books only your group still needs are shown greyed out.
- Works alongside map addons such as OpenMap.

**Minimap**

- Icons show for books within minimap range. Rotating minimaps, square minimaps, zoom levels and indoor/outdoor scale are all handled.
- The next book on your route stays pinned to the minimap edge even when it's out of range, so you always know which way to go.
- Hover shows the distance in yards. Shift-click and right-click work the same as on the world map.

---

## Optimized route

Turn the route on with the **Optimized route** button or `/bom route`.

- The route covers every book you still need, **lowest-level set first**. Within each set the order is optimized (nearest neighbour, then 2-opt) starting from your current position. Each set starts where the previous one ended. Trips between continents are penalized, so the route avoids crossing the sea back and forth.
- A **tracker** window shows the next book, its location and coordinates, the distance in yards and an arrow pointing toward it. Drag it anywhere; its position is saved.
  - **Skip**: skip the current book for this session and move to the next.
  - **Recalc**: forget skipped books and rebuild the route from where you are now.
  - **TomTom**: send the whole route to TomTom as numbered waypoints.
  - **×**: turn the route off.
- On the world map, the next few steps are **numbered** and joined by a dotted trail with a spark travelling along it.
- The route updates by itself when you collect the current book.
- `/bom route list` prints the full route in chat. `/bom route tomtom` sends it to TomTom.

---

## Group mode

When you're in a party or raid, every member who runs the addon shares their collection automatically over a hidden addon channel. Nothing is posted in chat.

- **Tooltips** on map pins and in the book list show who in your group has each book and who is still missing it.
- With **Also show the books my group is missing** turned on (the default), books a group member needs show on your map greyed out, so you can guide them there.
- The **Group** side tab shows each member as a grid of book icons in class colours, with their count.
- The minimap button / DataBroker tooltip shows every member's progress.
- Members running a version of the addon with a different book list are still listed, but their books can't be compared. Ask them to update.

To share progress with people who don't run the addon, use [`/bom share`](#slash-commands).

---

## Library rewards

Hand books in at the WoW Forever library to unlock rewards:

| Books | Reward | Choices |
|---|---|---|
| 10 | Necklace | Scholarly Pendant, Erudite's Amulet |
| 20 | Ring | Field Researcher's Loop, Philanthropist's Ring |
| 25 | Bow, crest or light | Truthseeker's Bow, Crest of Elucidation, Researcher's Night Light |

In the **Rewards** tab, hover over an item to see its tooltip, **Shift-click** to link it in chat, or **Ctrl-click** to try it on.

---

## Slash commands

`/bom` and `/books` are interchangeable.

| Command | What it does |
|---|---|
| `/bom` | Open or close the book list window |
| `/bom list` | Print every book in chat with its location and coordinates (green = collected) |
| `/bom next` | Show the nearest missing book and set a TomTom waypoint, or open the map there |
| `/bom route` | Turn the optimized route on or off |
| `/bom route list` | Print the full route in chat |
| `/bom route tomtom` | Send the whole route to TomTom |
| `/bom share` | Post your progress to your raid, party or (otherwise) guild |
| `/bom share group\|party\|raid\|guild\|say` | Post your progress to a specific channel |
| `/bom share [channel] missing` | Also post the names of the books you're missing |
| `/bom done N` | Mark book number *N* (from `/bom list`) as collected |
| `/bom undo N` | Mark book number *N* as not collected |
| `/bom toggle` | Show or hide the map icons |
| `/bom minimap` | Show or hide the minimap button |
| `/bom welcome` (or `/bom bvn`) | Open the welcome page |
| `/bom bug` | Show the Discord link for bug reports |
| `/bom reset` | Mark every book as not collected |
| `/bom ids` | Developer helper: print the item ID of every item in your bags |

---

## Book list

There are 39 books in total. One in the starting set is Alliance-only and one is Horde-only, so each character sees **38**.

<details>
<summary><b>Starting set</b> (16)</summary>

| Book | Location |
|---|---|
| Archmage Theocritus' Research Journal | Tower of Azora, Elwynn Forest (65.4, 70.1) |
| Archmage Antonidas: The Unabridged Autobiography | Ironforge (75.7, 10.5) |
| Bewitchments and Glamours | Moonbrook, Westfall (45.4, 70.4) |
| Rumi of Gnomeregan: The Collected Works *(Alliance)* | Sentinel Hill, Westfall (52.7, 53.8) or Thelsamar, Loch Modan (35.6, 48.9) |
| Crimes Against Anatomy | The Darkened Bank, Duskwood (16.6, 28.5) |
| Runes of the Sorcerer-Kings | Mo'grosh Stronghold, Loch Modan (77.4, 14.0) |
| Goaz Scrolls | Whelgar's Excavation Site, Wetlands (33.6, 47.9) |
| The Dalaran Digest, Vol. 23 | Ambermill, Silverpine Forest (63.5, 63.1) |
| Ataeric: On Arcane Curiosities | The Sepulcher, Silverpine Forest (43.4, 41.2) |
| The Apothecary's Metaphysical Primer | Brill, Tirisfal Glades (59.4, 52.3) |
| Nar'thalas Almanac, Vol. 74 | Ruins of Mathystra, Darkshore (59.6, 22.2) |
| Arcanic Systems Manual | The Sludge Fen, The Barrens (56.3, 8.8) |
| Baxtan: On Destructive Magics | Ratchet, The Barrens (62.7, 36.3) |
| Secrets of the Dreamers | Cavern of Mists, The Barrens (46.0, 36.5) |
| Fury of the Land | Grimtotem Post, Stonetalon Mountains (74.4, 85.7) |
| The Lessons of Ta'zo *(Horde)* | Ta'zo Mural, Orgrimmar (38.7, 78.4) |

</details>

<details>
<summary><b>Level 35 set</b> (8)</summary>

| Book | Location |
|---|---|
| Basilisks: Should Petrification be Feared? | Crystalvein Mine, Stranglethorn Vale (41.4, 50.9) |
| Geomancy: The Stone-Cold Truth | Darkcloud Pinnacle, Thousand Needles (34.4, 40.1) |
| Defensive Magics 101 | Gallows' Corner, Alterac Mountains (48.4, 57.6) |
| RwlRwlRwlRwl! | Witch Hill, Dustwallow Marsh (57.2, 20.8) |
| A Web of Lies: Debunking Myths and Legends | Witherbark Village, Arathi Highlands (73.6, 65.2) |
| Demons and You | Thunder Axe Fortress, Desolace (55.1, 26.2) |
| Mummies: A Guide to the Unsavory Undead | Badlands (56.7, 39.9) |
| A Ludite's Guide to Caring for Your Demonic Pet | Fallow Sanctuary, Swamp of Sorrows (61.4, 22.4) |

</details>

<details>
<summary><b>Level 45 set</b> (7)</summary>

| Book | Location |
|---|---|
| Sanguine Sorcery | Top of the Sunken Temple, Swamp of Sorrows (70.0, 51.0) |
| Legends of the Tidesages | Lost Rigger Cove, Tanaris (72.7, 47.8) |
| Everyday Etiquette | Haldarr Encampment, Azshara (20.7, 62.0) |
| Stonewrought Design | Blackrock Mountain tomb altar, Burning Steppes (29.0, 28.9) |
| Venomous Journeys | Shadra'Alor, The Hinterlands (36.0, 72.8) |
| A Mind of Metal | The Cauldron, Searing Gorge (37.8, 49.3) |
| Conjurer's Codex | Blasted Lands (55.4, 32.2) |

</details>

<details>
<summary><b>Level 60 set</b> (8)</summary>

| Book | Location |
|---|---|
| Magma or Lava? | Inside Blackrock Mountain, before the Blackrock Depths entrance (29.6, 28.2) |
| Northern Kalimdor - A Comprehensive Guide | Timbermaw Hold tunnel, Felwood (65.2, 3.3) |
| Undead Potatoes | Felstone Field, Western Plaguelands (38.3, 54.6) |
| The Knight and the Lady | Eastern Plaguelands (47.3, 42.3) |
| Scourge: Undead Menace or Misunderstood? | Eastern Plaguelands (31.3, 21.0) |
| A Study of the Light | Light's Hope Chapel, Eastern Plaguelands (71.8, 48.2) |
| Ka-Boom! | Everlook, Winterspring (60.7, 37.7) |
| Necromancy 101 | Caer Darrow keep, Western Plaguelands (69.4, 72.8) |

</details>

The data lives in [`Data/Books.lua`](Books_on_map_Forever/Data/Books.lua). Sources: [foreverchanges.pro](https://foreverchanges.pro/library-books), [zockify.com](https://www.zockify.com/forever/library-books/), [Warcraft Tavern](https://www.warcrafttavern.com/forever/guides/library-books/) and Wowhead.

---

## Optional addons

None are required. The addon detects them and uses them if they're installed:

- **TomTom**: waypoints from map pins, the book list, `/bom next` and the route.
- **DataBroker displays** (Titan Panel, ChocolateBar, ElvUI, Bazooka…): a *Books* launcher showing `collected/total`. Left-click opens the list, right-click toggles map icons.
- **Minimap button managers** (Leatrix Plus, SexyMap, button bags…): the button uses LibDBIcon, so they handle it like any other.
- **OpenMap**: pins are drawn above its stitched map art.

---

## Saved data

Stored in `WTF\Account\<account>\…\SavedVariables`:

| Variable | Scope | Contents |
|---|---|---|
| `BooksOnMapForeverDB` | Per character | Collected books, all settings, language, folded sections, route state and tracker position, minimap button position |
| `BooksOnMapForeverGlobal` | Account-wide | Whether the welcome page has been seen |

Each character has its own collection. Settings are also per character.

---

## Troubleshooting

**A book I picked up wasn't checked off.**
Detection runs when your bags change and checks item IDs first, then the English or French item name. Open your bags once, or `/reload`. You can always tick it by hand in the list, Shift-click its map pin, or use `/bom done N`.

**Books I already handed in still show.**
Handed-in books are detected at login from completed library quests. Type `/reload`. If one still shows, tick it by hand.

**No icons on the map.**
Check **Show on the map** in the options, or type `/bom toggle`. Collected books never show on the map. If every book is marked as collected (for example after **Hide all**), click **Show all** or type `/bom reset`.

**The language didn't change.**
Changing the language reloads the UI. If you cancelled the reload prompt, pick the language again.

**My group member doesn't appear in the Group tab.**
They must have the addon installed and enabled, and be in your party or raid. If they're listed as using another version, one of you needs to update.

**Reporting a bug**
Use `/bom bug` or the **Bug** button to copy the developer's Discord link. Include the error text if you have one; an error display addon such as BugSack makes that easier.

---

## About this fork

This repository is a fork of [EfkaBz/Books-on-Map-Forever](https://github.com/EfkaBz/Books-on-Map-Forever) with local fixes on top of the upstream code.

### Fixes

| Fix | File | Details |
|---|---|---|
| Minimap pins redraw only on change | [`modules/MinimapPins.lua`](Books_on_map_Forever/modules/MinimapPins.lua) | Upstream recalculated every minimap pin 20 times a second, even while standing still. Now it still checks 20 times a second but only redraws when your position, facing, minimap zoom or indoor state changes, plus once a second for changes nothing reports (group needs, route steps). |

### Re-applying fixes after an upstream update

1. Fetch upstream: `git fetch upstream`.
2. Merge or rebase `upstream/main` onto this fork's `main`.
3. Check each file in the table above still has its fix. If upstream rewrote the file, port the change by hand.
4. Deploy only the addon folder to the game (no `.git`), e.g.
   `robocopy Books_on_map_Forever "<WoW Forever>\Interface\AddOns\Books_on_map_Forever" /E`
   Run it with `/L` first to see what it would overwrite.

### Checking the code

The addon targets Lua 5.1. Syntax-check a file with `luac -p <file>`.

---

## Credits

- **Daeler / Efka**: original author ([EfkaBz/Books-on-Map-Forever](https://github.com/EfkaBz/Books-on-Map-Forever)).
- Libraries: LibStub, CallbackHandler-1.0, LibDataBroker-1.1, LibDBIcon-1.0.
- Book and reward data: foreverchanges.pro, zockify.com, Warcraft Tavern, Wowhead.

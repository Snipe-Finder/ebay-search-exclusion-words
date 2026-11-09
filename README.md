# eBay search exclusion words

Hand-picked words and phrases for leaving junk out of eBay searches and listing alerts: fakes, empty boxes, parts, accessories, locked phones and the like. There are twelve lists, one for each kind of item.

Made by [Snipe Finder](https://snipefinder.com/?ref=github), a free eBay listing alert service that I run. This project isn't affiliated with eBay.

## The lists

| List | What it leaves out | Words | Exceptions |
|---|---|---|---|
| [Pokémon cards](lists/pokemon-cards.txt) | Proxies and custom cards, digital code cards, empty, opened or resealed boxes, repacks and mystery packs, "PSA ready" raw cards, sleeves, binders, playmats and cases, metal and art cards | 28 | [2](lists/pokemon-cards.exceptions.txt) |
| [Labubu figures](lists/labubu.txt) | Fakes ("lafufu"), Labubu trading cards, clothes and outfits for the figures, cases and stickers, crochet patterns, handmade and custom items, keychains on their own | 25 | [5](lists/labubu.exceptions.txt) |
| [LEGO sets](lists/lego.txt) | Compatible and unofficial bricks, light kits, display cases and stands, instructions or boxes on their own, minifigures on their own, incomplete sets, sets without minifigures | 35 | [3](lists/lego.exceptions.txt) |
| [Graphics cards](lists/graphics-cards.txt) | Broken, faulty or untested cards, empty boxes, photos of a card, whole PCs and laptops, coolers, backplates and water blocks | 29 | – |
| [iPhones](lists/iphones.txt) | Cases and screen protectors, iCloud, activation and MDM locked phones, blacklisted or bad IMEI, cracked or broken phones, housings and parts, replicas and dummies, empty boxes | 30 | [7](lists/iphones.exceptions.txt) |
| [MacBooks](lists/macbooks.txt) | Logic boards, screens, top cases and other parts, shells and keyboard covers, chargers or boxes on their own, locked machines, cracked or broken ones | 25 | [6](lists/macbooks.exceptions.txt) |
| [Game consoles](lists/game-consoles.txt) | Broken or banned consoles, empty boxes, skins and faceplates, controllers, docks or cases on their own, Japanese versions | 19 | [2](lists/game-consoles.exceptions.txt) |
| [Retro games](lists/retro-games.txt) | Reproductions, bootlegs, homebrew and ROM hacks, flash carts, manuals, boxes, cases or labels on their own, replacement shells, broken items | 22 | [5](lists/retro-games.exceptions.txt) |
| [Sneakers](lists/sneakers.txt) | Replicas and knock-offs, kids' sizes (PS, TD, GS, toddler, youth), empty boxes, laces or insoles on their own, clothing, keychains, posters and stickers | 28 | – |
| [Watches](lists/watches.txt) | Homages, replicas and Seiko mods, straps, bands and bracelets on their own, dials, bezels, movements, boxes or papers on their own, watches for parts or repair | 27 | – |
| [Sports cards](lists/sports-cards.txt) | Reprints, customs and proxies, novelty and digital cards, facsimiles, "PSA ready" and other ungraded cards | 14 | – |
| [Camera lenses](lists/camera-lenses.txt) | Lenses with fungus, haze or separation, broken lenses or ones for parts, caps, hoods and filters on their own, mount adapters and lens collars | 22 | [7](lists/camera-lenses.exceptions.txt) |

Each list comes in three forms:

- `lists/<name>.txt`: one word or phrase per line.
- `comma-separated/<name>.txt`: the same list on one line, ready to paste into a box.
- `lists.json`: every list, for use in code.

## How to use them

### In an alert tool

Paste the comma-separated file into the tool's box for excluded words.

In Snipe Finder, that's **Excluded keywords**. The exceptions file goes in **Exceptions to excluded keywords**, which appears in Advanced mode.

Check how your tool matches words first. These lists assume whole-word matching, where `case` doesn't catch `showcase`. That's why some entries are phrases, such as `case for` and `box only`, rather than single words. A tool that matches inside words will leave out more than you want.

### In eBay's own search

eBay's search box leaves out a word if you put a minus sign in front of it, as in `-proxy`. A search with dozens of exclusions gets long, so pick the handful that matter most for what you're looking for. Entries of two or more words may not work as a single phrase there.

### Exceptions

Some lists have a second file of exceptions: words that mean a listing should be kept even though it contains an excluded word. For example, the Pokémon list leaves out `fake`, but keeps a listing that says `not fake`. Exceptions only help in tools that support them.

## Things to know

- The lists are made for English-language titles, mainly on eBay US and UK.
- Some lists assume a particular kind of search:
  - The sports card list leaves out ungraded and raw cards, because it was made for graded-card searches.
  - The graphics card list leaves out whole PCs and laptops, because it was made for cards on their own.
  - Remove those entries if they don't fit what you're after.
- The sneaker list has `(ps)`, `(td)` and `(gs)` in brackets, the way sellers often mark kids' sizes. That's less likely to catch unrelated titles than the bare letters would.
- The lists are tuned by hand, so they'll miss things and occasionally catch a listing you wanted. Suggestions are welcome.

## Suggest a word

Open an issue. Say which list it's for, give the word or phrase, and show an example of the kind of title it would catch. Please leave out links to listings and sellers' names.

## Licence

[CC BY 4.0](LICENSE). You can copy, change and reuse the lists, including commercially, as long as you credit the source. A credit like this is enough:

> Exclusion lists by Snipe Finder (https://snipefinder.com)

eBay is a trademark of eBay Inc. This project isn't affiliated with, sponsored by or endorsed by eBay.

Last updated 9 November 2026.

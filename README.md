# Map Companion item data

The item database of [Map Companion](https://github.com/Divine4k/poeapp), kept apart from the app's code so that a token allowed to write here can never change the app.

## items.json

One entry per picture of an item as it looks in the game's inventory:

| Field | Meaning |
| --- | --- |
| `name` | The item, spelled as on poe.ninja |
| `print` | The picture's fingerprint: 486 signed bytes, base64 (13 by 13 colour blocks, stack-number corner left out) |
| `by` | Who named it |
| `auto` | `1` when an app learned it by itself from a clear read, absent when a person typed the name |
| `at` | When, in milliseconds since 1970 |

Every copy of the app downloads this file at start. Apps with an upload token add to it. It stays small: the same picture is never added twice, an item gets at most three pictures named by people and one learned by an app, and the list stops at 4,000 entries (about 3 MB).

## reports/

Troubleshooting reports sent from the app with the report key: the inventory slots as the app saw them, nothing else from the screen.

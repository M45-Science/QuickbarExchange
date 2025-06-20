# M45 Quickbar Exchange (Format V2)

Share your custom quickbar setups using compressed, Base64-encoded strings.

---

## 🚀 How It Works

- Code embeds support for M45 Quickbar Exchange **V2** using string compression via `zlib` and Base64 encoding through `LuaHelpers.encode_string`.
- The header `M45-QB2=` identifies the format version.
- Each quickbar slot is encoded as:
  ```
  slot-alias[:quality-alias]
  ```
- Up to **100 slots** are included. Empty slots appear as empty commas (`,,`).

---

## Slot Aliases

Instead of lengthy item names, slot aliases (e.g. `AA`, `AB`, `AC`, ...) are auto-generated using the included item list. They map to in-game prototypes via lookup tables.

---

## Quality Aliases

Inventory quality is shortened using single-character codes:

| Alias | Meaning     |
|-------|-------------|
| `u`   | uncommon    |
| `r`   | rare        |
| `e`   | epic        |
| `l`   | legendary   |

Items with **normal** quality leave out this suffix.

---

## Format Summary

```
M45-QB2=alias[:quality],alias[:quality],...,alias[:quality]
```

- Slot alias must map to a valid item in the mod’s list.
- Quality is appended when != normal.
- Padding with commas extends up to 100 slots.

---

## Example

```
M45-QB2=AA,AB:l,AC:u,AD,AE:r,,,,,... (total 100 entries)
```

This string represents:
- `AA` – first item, normal quality  
- `AB:l` – second item, legendary  
- `AC:u` – third item, uncommon  
- `AD` – fourth, normal  
- `AE:r` – fifth, rare  
- Remaining slots are empty.

---

## In-Game Usage

### Export Quickbar
```lua
QUICKBAR_MakeExchangeWindow(player, true)
```
- Opens a window with the encoded string for copying.

### Import Quickbar
- Paste an encoded string into the window and click **Import**.
- The mod parses, decodes, and populates your quickbar up to 100 slots.
- Skips invalid items/qualities and notifies you of any issues.

---

## Quick Start

1. Copy `quickbar.lua` into your `control.lua` or equivalent.
2. Ensure its required helper functions and `prototypes` tables are available.
3. Use the export/import UI buttons to exchange your setup.

---

## Notes

- Version **MPL 2.0**, authored by Carl Frank Otto III (`carlotto81@gmail.com`).
- Slot alias generation is dynamic and based on an internal item list—ensure your mod uses the same version for compatibility.
- This format supersedes **V1**, offering improved flexibility with quality support and built-in aliasing.

---

## Visual Example

![Example Quickbar GUI](https://raw.githubusercontent.com/M45-Science/M45-Quickbar-Exchange/refs/heads/main/example-bar.png)

You can find the reference `quickbar.lua` implementation [here](../quickbar.lua).

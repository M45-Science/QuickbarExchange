# M45 Quickbar Exchange Format V2

The quickbar exchange string allows players to share their quickbar setup. The data is compressed using `zlib` and Base64 encoded via [LuaHelpers.encode_string](https://lua-api.factorio.com/latest/classes/LuaHelpers.html#encode_string).

## Format

```
M45-QB2=slot-name[:quality],slot-name[:quality],...
```

- `slot-name` is the item prototype name for each quickbar slot.
- `quality` is optional and shortened using the following aliases:
  - `u` – `uncommon`
  - `r` – `rare`
  - `e` – `epic`
  - `l` – `legendary`

Qualities are omitted for normal items. Up to 100 slots are encoded with empty entries represented by consecutive commas.

## Example

```
eJytULFuQzEI/CGzVO0SqUv3Dv0E7EcdFAwW8KJ+fp2katTMZTh0h0DcvT+/wMfb02skkUA7UuRBSqQ5doJEPR280Nd0ioB01JjmCZUkf+VdN/LutvrfQUzhTPLyiZHAGuQXJqYdjri2trtYdzndWQwUARJq6dxgmlAZtPE+HsTK/UGJvUZismmZPOkKkAa3B4sjyxUguCtKwZZ8JphuZ14+bhkUt2oXpz+fCI5Zmum6rAnNRmXFFVL55/oGHhWH8Q==
```

This 260‑byte string encodes 20 items, including `steel-chest:l` and `storage-tank:r`, followed by 80 empty slots.

Visual:

![Test Quickbar](https://raw.githubusercontent.com/M45-Science/M45-Quickbar-Exchange/refs/heads/main/example-bar.png)

Example implementation: [quickbar.lua](../quickbar.lua)

# CopyMapHub v1

**CMH** — CopyMapHub, v1.

Standalone build. Serialises a running place to an `.rbxl` file using the
chunked `INST` / `PROP` / `PRNT` binary format.

## Requirements

Runs under a patched client that provides the executor APIs this script
depends on (`getgenv`, `loadstring`, `gethiddenproperty`, `getscriptbytecode`,
`readfile` / `writefile`). It does not run in stock Roblox Studio or a normal
published game.

## Notes

- Save as **binary** (`.rbxl`). XML output loses precision on some properties.
- Server-side content (`ServerStorage`, `ServerScriptService`, server scripts)
  is not recoverable from the client. This is a Roblox engine restriction.
- **Save binary format.** `FILE -> Save to File As`, filename ending `.rbxl`.
- **Character not spawning.** Move leftover scripts out of `StarterPlayer`, then
  run `game:GetService("Players").CharacterAutoLoads = true` in the Command Bar.
  Use *Play Here* rather than *Play* to spawn at your current camera.
- **Chat not working.** Clear `Chat` and `TextChatService` children.

## License

**GNU AGPL-3.0** — see [`LICENSE`](LICENSE).

This project is a derivative of
[UniversalSynSaveInstance](https://github.com/luau/UniversalSynSaveInstance),
which is AGPL-3.0. The notice must be retained in any redistribution.

### Inlined dependencies

| Component | Source |
|---|---|
| StreamBuffer | [`luau/SomeHub`](https://github.com/luau/SomeHub) — `StreamBuffer.luau` |
| UniversalMethodFinder | [`luau/SomeHub`](https://github.com/luau/SomeHub) — `UniversalMethodFinder.luau` |
| Base64 | [`daily3014/rbx-algorithms`](https://github.com/daily3014/rbx-algorithms) |
| llz4 | [`RiskoZS/llz4`](https://github.com/RiskoZS/llz4) |
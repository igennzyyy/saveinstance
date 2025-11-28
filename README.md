# Universal SaveInstance - Modified
![Roblox](https://img.shields.io/badge/Platform-Roblox-red)
![Lua](https://img.shields.io/badge/Language-Lua-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Deskripsi

Script SaveInstance yang telah dimodifikasi untuk menyimpan:
- ✅ **Script Original (Bytecode)** - Menyimpan source code asli dari semua scripts
- ✅ **Terrain Data** - Menyimpan data terrain lengkap
- ✅ **Semua Instance** - Menyimpan seluruh game/place

Script ini adalah modifikasi dari [UniversalSynSaveInstance](https://github.com/luau/SomeHub) dengan penambahan fitur untuk memastikan script original dan terrain tersimpan dengan baik.

---

## 🚀 Cara Penggunaan

### Metode 1: Load Langsung dari GitHub (Recommended)
```lua
-- Load script dari GitHub Anda
local synsaveinstance = loadstring(game:HttpGet("https://raw.githubusercontent.com/USERNAME/REPO_NAME/main/saveinstance.lua"))()

-- Jalankan dengan default settings (SaveBytecode & SaveTerrain sudah aktif)
synsaveinstance()
```

### Metode 2: Dengan Custom Options
```lua
-- Load script
local synsaveinstance = loadstring(game:HttpGet("https://raw.githubusercontent.com/USERNAME/REPO_NAME/main/saveinstance.lua"))()

-- Custom options
local options = {
    mode = "full",                  -- Mode: "full", "optimized", atau "scripts"
    SaveBytecode = true,            -- Simpan script original
    SaveTerrain = true,             -- Simpan terrain
    FilePath = "MyGame_Complete",   -- Nama file output
    ShowStatus = true,              -- Tampilkan progress
    timeout = 20,                   -- Timeout decompile (detik)
}

-- Execute
synsaveinstance(options)
```

### Metode 3: Download & Load Local
```lua
-- Download file saveinstance.lua ke folder executor
-- Lalu load:
loadstring(readfile("saveinstance.lua"))()
```

---

## ⚙️ Fitur & Options

### Default Settings (Sudah Aktif)
| Option | Value | Deskripsi |
|--------|-------|-----------|
| `SaveBytecode` | `true` | Menyimpan bytecode original dari scripts |
| `SaveTerrain` | `true` | Menyimpan data terrain |
| `scriptcache` | `true` | Aktifkan cache untuk bytecode |
| `mode` | `"optimized"` | Mode penyimpanan optimized |

### Custom Options yang Tersedia
```lua
{
    -- Script Options
    SaveBytecode = true,          -- Simpan bytecode asli
    scriptcache = true,           -- Cache bytecode
    Decompile = true,             -- Decompile scripts
    noscripts = false,            -- Jangan skip scripts
    timeout = 15,                 -- Timeout decompile (detik)

    -- Terrain Options
    SaveTerrain = true,           -- Simpan terrain

    -- General Options
    mode = "full",                -- "full", "optimized", "scripts"
    ShowStatus = true,            -- Tampilkan progress
    IgnoreDefaultProperties = true,

    -- Safety Options
    SafeMode = false,             -- Kick sebelum save
    ShutdownWhenDone = false,     -- Shutdown setelah selesai
    AntiIdle = true,              -- Prevent idle kick

    -- File Options
    FilePath = "OutputFileName",  -- Nama file (tanpa ekstensi)
}
```

---

## 📁 Output File

File akan tersimpan di folder executor dengan format:
- **Place/Game**: `place_[PlaceID]_[Name].rbxlx`
- **Model**: `model_[Name].rbxmx`
- **Custom**: `[FilePath].rbxlx` atau `.rbxmx`

---

## 🛠️ Executor yang Didukung

Script ini kompatibel dengan executor yang memiliki:
- ✅ `getscriptbytecode` / `dumpstring` function
- ✅ `decompile` function (optional, untuk decompile scripts)
- ✅ `writefile` / `appendfile` function
- ✅ `readfile` function
- ✅ `base64encode` function

**Tested on:**
- Synapse X
- Script-Ware
- Solara
- Electron
- Wave

---

## 📝 Changelog

### Version 1.0 (Modified - 2025-11-28)
- ✅ Added `SaveBytecode = true` by default
- ✅ Added `SaveTerrain = true` by default
- ✅ Ensured script original always saved
- ✅ Ensured terrain data always saved

---

## ⚠️ Disclaimer

- Script ini hanya untuk **educational purposes**
- Gunakan dengan bijak dan tanggung jawab Anda sendiri
- Tidak bertanggung jawab atas penyalahgunaan script ini
- Pastikan Anda memiliki izin untuk menyimpan game/place yang Anda akses

---

## 📞 Support & Contact

- **Original Source**: [UniversalSynSaveInstance](https://github.com/luau/SomeHub)
- **Modified by**: [Your Name]
- **Issues**: [GitHub Issues](https://github.com/USERNAME/REPO_NAME/issues)

---

## 📜 License

MIT License - Free to use and modify

---

## 🙏 Credits

- Original script by [luau/SomeHub](https://github.com/luau/SomeHub)
- Modified for enhanced script & terrain saving

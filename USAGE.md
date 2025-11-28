# 📖 Panduan Lengkap Penggunaan

## 1. Setup Awal

### Install Git (Jika belum)
- **Windows**: Download dari [git-scm.com](https://git-scm.com/)
- **Mac**: `brew install git`
- **Linux**: `sudo apt-get install git`

### Buat Akun GitHub
1. Kunjungi [github.com](https://github.com)
2. Sign up dengan email Anda
3. Verifikasi email

---

## 2. Upload Script ke GitHub

### Cara 1: Via GitHub Web (Mudah untuk Pemula)

1. **Login ke GitHub**
2. **Klik tombol "+" di pojok kanan atas** → New repository
3. **Isi data repository:**
   - Repository name: `saveinstance-modified` (atau nama lain)
   - Description: "Modified SaveInstance with bytecode & terrain support"
   - Public/Private: Pilih Public
   - ✅ Add README file
   - License: MIT License
4. **Klik "Create repository"**
5. **Upload file:**
   - Klik "Add file" → "Upload files"
   - Drag & drop file `saveinstance.lua`
   - Commit changes

### Cara 2: Via Git Command Line (Lebih Profesional)

```bash
# 1. Buat folder project
mkdir saveinstance-modified
cd saveinstance-modified

# 2. Initialize git
git init

# 3. Copy file saveinstance.lua ke folder ini

# 4. Tambahkan file
git add saveinstance.lua
git add README.md
git add LICENSE

# 5. Commit
git commit -m "Initial commit: SaveInstance with bytecode & terrain"

# 6. Hubungkan dengan GitHub (ganti USERNAME dan REPO_NAME)
git remote add origin https://github.com/USERNAME/REPO_NAME.git

# 7. Push ke GitHub
git branch -M main
git push -u origin main
```

---

## 3. Menggunakan Script

### Dari GitHub (Raw URL)

```lua
-- Format URL:
-- https://raw.githubusercontent.com/USERNAME/REPO_NAME/main/saveinstance.lua

-- Contoh:
local synsaveinstance = loadstring(game:HttpGet("https://raw.githubusercontent.com/yourusername/saveinstance-modified/main/saveinstance.lua"))()

-- Execute
synsaveinstance()
```

### Dengan Custom Options

```lua
local synsaveinstance = loadstring(game:HttpGet("YOUR_GITHUB_RAW_URL"))()

synsaveinstance({
    mode = "full",
    FilePath = "MyAwesomeGame",
    ShowStatus = true,
    timeout = 30
})
```

---

## 4. Update Script di GitHub

### Via Web
1. Buka file di GitHub
2. Klik icon pensil (Edit)
3. Edit file
4. Commit changes

### Via Git
```bash
# 1. Edit file lokal
# 2. Add & commit
git add saveinstance.lua
git commit -m "Update: improved terrain saving"

# 3. Push
git push origin main
```

---

## 5. Tips & Best Practices

### ✅ DO:
- Selalu test script sebelum push
- Tulis commit message yang jelas
- Update README jika ada perubahan fitur
- Tambahkan version tag untuk releases

### ❌ DON'T:
- Jangan hardcode credentials/tokens
- Jangan upload file besar (>100MB)
- Jangan gunakan script untuk hal ilegal

---

## 6. Troubleshooting

### Error: "Unable to load script"
- Pastikan URL raw GitHub benar
- Check internet connection
- Pastikan repository public (bukan private)

### Error: "loadstring is not available"
- Executor Anda tidak support loadstring
- Gunakan metode download & readfile

### Script tidak save terrain
- Pastikan `SaveTerrain = true`
- Check executor support untuk terrain API

---

## 7. Advanced Usage

### Load dari Private Repository
```lua
-- Perlu GitHub token untuk private repo
local token = "ghp_your_token_here"
local url = "https://raw.githubusercontent.com/username/private-repo/main/saveinstance.lua"

local headers = {
    ["Authorization"] = "token " .. token
}

local response = request({
    Url = url,
    Method = "GET",
    Headers = headers
})

loadstring(response.Body)()
```

### Auto-Update Script
```lua
-- Check version & auto-update
local VERSION = "1.0.0"
local VERSION_URL = "https://raw.githubusercontent.com/username/repo/main/version.txt"

local latest = game:HttpGet(VERSION_URL)
if latest ~= VERSION then
    print("New version available! Updating...")
    -- Download & load new version
end
```

---

## 📞 Need Help?

- Open issue di GitHub: [Issues](https://github.com/USERNAME/REPO_NAME/issues)
- Check documentation: [README.md](README.md)

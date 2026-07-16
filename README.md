# Codex Pets

这是一个可分享的 Codex 自定义 Pet 集合。

## 下载

在 GitHub 仓库页面点击 **Code → Download ZIP**，或使用 Git 克隆：

```bash
git clone https://github.com/The-time-forever/Codex-Pets.git
```

下载或克隆后，进入本仓库目录。每个 Pet 都必须保留自己的完整文件夹，例如：

```text
Codex-Pets/
└── The Spike Cross/
    ├── hari-midnight/
    │   ├── pet.json
    │   └── spritesheet.webp
    └── xu-sha-la/
        ├── pet.json
        └── spritesheet.webp
```

## 安装

### Windows PowerShell

将整个 Pet 文件夹复制到当前用户的 Codex Pet 目录：

```powershell
$pets = Join-Path $env:USERPROFILE ".codex\pets"
$source = ".\The Spike Cross"
New-Item -ItemType Directory -Force $pets | Out-Null
Copy-Item -Recurse -Force "$source\hari-midnight", "$source\xu-sha-la" $pets
```

如果只想安装其中一个，例如 `hari-midnight`：

```powershell
$pets = Join-Path $env:USERPROFILE ".codex\pets"
New-Item -ItemType Directory -Force $pets | Out-Null
Copy-Item -Recurse -Force ".\The Spike Cross\hari-midnight" $pets
```

### macOS / Linux

```bash
mkdir -p "$HOME/.codex/pets"
cp -R "./The Spike Cross/hari-midnight" "./The Spike Cross/xu-sha-la" "$HOME/.codex/pets/"
```

安装完成后，重启 Codex，让应用重新读取 Pet 文件。安装后的目录应类似：

```text
Windows: %USERPROFILE%\.codex\pets\hari-midnight\pet.json
macOS/Linux: ~/.codex/pets/hari-midnight/pet.json
```

## 注意事项

- 必须复制整个 Pet 文件夹，不能只复制 `spritesheet.webp`。
- `pet.json` 和 `spritesheet.webp` 必须位于同一文件夹内。
- 不要修改 `pet.json` 中的 `id`，否则可能导致 Pet 重复或无法识别。
- 如果目标目录中已有同名 Pet，复制时会覆盖旧版本；如需保留旧版本，请先备份。
- 这些 Pet 使用 `spriteVersionNumber: 2`，需要支持 Codex 自定义 Pet 的版本。

## 贡献

欢迎提交新的 Pet、动画素材、安装改进或文档修正。

1. Fork 本仓库并创建一个新的分支。
2. 在合适的分类目录下添加或修改 Pet 文件夹。
3. 确保每个 Pet 文件夹同时包含 `pet.json` 和 `spritesheet.webp`。
4. 保持 `pet.json` 中的 `id` 与文件夹名称一致，并使用唯一的 `id`。
5. 本地确认文件结构和安装说明无误后，提交 Commit 并推送分支。
6. 创建 Pull Request，并简要说明改动内容。

提交新 Pet 时，请尽量附上 Pet 名称、简短介绍、预览图或演示说明，方便审核和使用。

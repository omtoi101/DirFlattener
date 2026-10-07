# Folder Flattener

Move files from nested subfolders into the top-level folder, then remove now-empty subfolders safely. Emphasis on 0 data-loss.

## Features

- **Dry run by default** — preview changes before applying
- **Safe renaming** — never overwrites; conflicts become `name_2.ext`, `name_3.ext`
- **Symlink-aware** — moves symlinks as links, not their targets
- **Integrity check** — confirms item count matches before/after

## Usage

```bash
# Preview (dry run)
python3 main.py /path/to/folder

# Apply changes
python3 main.py /path/to/folder --apply
```

## Example

```bash
# Before: 10 files scattered across 5 subfolders
└── photos/
    ├── 2024/
    │   ├── vacation.jpg
    │   └── weekend.png
    └── work/
        └── screenshot.gif

# After:
├── vacation.jpg
├── weekend.png
├── screenshot.gif
└── photos/  # empty, removed
```

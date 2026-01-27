# find-best-images

**Image deduplication and quality-based selection tool**

**[GitHub Repository](https://github.com/djdarcy/find-best-images)** | **Status: Active**

> Scan directories for similar images, evaluate them using objective quality metrics, and organize the highest-quality version of each group. Designed for deduplication and dataset curation at scale.

---

## The Problem

You have thousands of images across multiple directories — different versions, resizes, format conversions, and near-duplicates. Which version of each image is the best quality?

**Manual review**: Hours comparing similar images side-by-side, checking dimensions, formats, and file sizes.

**The cost**:
- Duplicate storage waste
- Inconsistent quality across collections
- No reliable way to identify which version is highest resolution or best format
- Manual comparison doesn't scale beyond a few hundred images

---

## The Solution

```bash
python find_best_images.py -i ./photos_camera -i ./photos_phone -o ./best_photos -r
# Groups similar images, selects highest-quality version of each
```

**CLIP-based similarity detection + objective quality metrics = automated deduplication and best-version selection.**

---

## Features

### CLIP-Based Similarity Detection
- Uses OpenAI's **CLIP model** (clip-vit-base-patch32) to generate semantic embeddings
- Groups images by cosine similarity with configurable thresholds
- Preset similarity levels: `same`, `almost_same`, `very_similar`, `similar`, and more
- Optional **region-based checking** (center, corners) for more accurate comparison

### Objective Quality Evaluation
Selects the best image from each group using measurable quality metrics:

- **Dimensions** — Pixel width × height (larger is better)
- **Resolution** — DPI/pixel density (higher is better for print)
- **Filesize** — Larger files typically retain more detail (same-format comparison)
- **Format quality** — Ranked by losslessness: PNG (100) > TIFF (95) > BMP (90) > WebP (85) > JPEG (75) > GIF (60)
- **Modified/Created date** — Prefer newest or oldest based on your needs

### Hybrid Scoring System
- **Primary metrics** evaluated in strict priority order (first metric wins unless tied)
- **Secondary metrics** with configurable weights for tie-breaking
- Ensures deterministic, reproducible selection

### Multi-Directory Scanning
- Scan multiple input directories simultaneously
- Recursive subdirectory traversal
- Include/exclude patterns (glob or regex) for both directories and files

### Flexible File Operations
- **Symlink** — Fast, space-efficient (default)
- **Copy** — Safe, independent copies
- **Move** — Relocate originals with optional backlinks to original location

### Output Organization
```
Output/
├── image_group_WxH_candidates/
│   ├── best_image.jpg              (highest quality version)
│   └── _candidates/
│       ├── duplicate_1.jpg         (lower quality versions)
│       ├── duplicate_2.png
│       └── metadata.txt
└── _singletons/                    (unique images, no duplicates found)
    └── unique_image.jpg
```

### Robust File Handling
- **Collision strategies**: hierarchical, hash, numeric, parent-only
- **Long path management**: Handles Windows 260-char path limits
- **Embedding cache**: Save computed CLIP embeddings to `.embedding_cache.pkl` for reuse
- **Dry run mode**: Preview all operations without modifying files

---

## Use Cases

### Digital Asset Deduplication
Consolidate photo collections from multiple devices:
```bash
python find_best_images.py \
  -i "D:\Photos\Camera" -i "D:\Photos\Phone" -i "D:\Photos\Backup" \
  -o "D:\Photos\Best" --recursive --copy-best
```

### AI Dataset Curation
Select the highest-quality version of each training image:
```bash
python find_best_images.py \
  -i "D:\datasets\raw" --recursive --copy-best --collect-results \
  --include-dirs-pattern "(__training|input)" \
  --exclude-dirs-pattern "(output|wip)" \
  --pattern-mode regex \
  --output-dir "D:\datasets\curated" --force
```

### Creative Workflow Organization
Organize game assets or photography projects:
```bash
python find_best_images.py \
  -i "./assets" -o "./organized" -r \
  --primary-metrics dimensions format_quality filesize \
  --similarity-preset very_similar \
  --collect-results
```

---

## Installation

```bash
# Clone and install
git clone https://github.com/djdarcy/find-best-images.git
cd find-best-images
pip install -r requirements.txt

# Or install in editable mode
pip install -e .
```

### Requirements
- Python 3.x
- PyTorch (for CLIP model inference)
- Transformers (Hugging Face, for CLIP)
- Pillow (image processing)
- tqdm (progress bars)

---

## Command Reference

| Option | Description |
|--------|-------------|
| `-i`, `--input-dir` | Input directories to scan (multiple allowed) |
| `-o`, `--output-dir` | Directory for organized output |
| `-r`, `--recursive` | Recursively scan subdirectories |
| `--copy-best` | Copy best images instead of symlinking |
| `--collect-results` | Consolidate best images into single directory |
| `--primary-metrics` | Quality metrics in strict priority order |
| `--secondary-metrics` | Tie-breaking metrics with weights |
| `--metric-weights` | Weights for secondary metrics (e.g., `dimensions:1.0,filesize:0.5`) |
| `--similarity-preset` | Similarity threshold preset (same, almost_same, very_similar, similar) |
| `--check-regions` | Number of image regions to compare for accuracy |
| `--include-dirs-pattern` | Include only matching directories |
| `--exclude-dirs-pattern` | Exclude matching directories |
| `--pattern-mode` | Pattern mode: `glob` (default) or `regex` |
| `--dryrun` | Preview operations without modifying files |
| `--force` | Overwrite existing output directories |
| `--date-preference` | Prefer `newest` or `oldest` when using date metrics |

---

## How It Works

1. **Discover** — Recursively scan input directories, validate image files
2. **Embed** — Compute CLIP embeddings for each image (cached for reuse)
3. **Group** — Cluster similar images by cosine similarity threshold
4. **Evaluate** — Score each group member using primary + secondary quality metrics
5. **Organize** — Place best version as primary, others as candidates in subfolders

---

## Relationship to ImgCompare

find-best-images shares a Python virtual environment with [ImgCompare](https://github.com/DazzleML/ImgCompare) (via symlink). Both use CLIP embeddings for similarity detection, but serve different purposes:

- **ImgCompare**: Compare two images or organize a directory by similarity grouping
- **find-best-images**: Find and select the highest-quality version from groups of similar/duplicate images across multiple directories

They are independent tools with no code dependencies between them.

---

## Technical Requirements

- Python 3.x
- GPU recommended for faster CLIP inference (CUDA), falls back to CPU
- 8GB+ RAM recommended for large collections

---

## License

GPL 3.0 — See repository for details

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**

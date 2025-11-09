# find-best-images

**AI-powered image curation tool**

**[GitHub Repository](https://github.com/djdarcy/find-best-images)** | **Status: Active**

> Find the best images from large collections using AI analysis of composition, quality, and aesthetics.

---

## The Problem

You generate 1,000 images. Which 10 are worth keeping?

**Manual review**: Hours of clicking through images, comparing quality, making subjective decisions.

**The cost**:
- 1,000 images × 3 seconds each = 50 minutes minimum
- Mental fatigue reduces accuracy
- Inconsistent criteria across sessions
- Miss hidden gems

---

## The Solution

```bash
find-best-images --dir ./generations --top 10 --output best/
# AI analyzes all images, exports top 10 to best/
```

**AI does in seconds what takes humans hours.**

---

## Features

### AI Quality Analysis
- **Composition scoring** - Rule of thirds, balance, framing
- **Sharpness detection** - Focus quality, blur detection
- **Aesthetic evaluation** - Color harmony, visual appeal
- **Technical quality** - Exposure, noise, artifacts

### Batch Processing
- Analyze thousands of images quickly
- Parallel processing for speed
- Progress tracking for large collections
- Resumable operations

### Customizable Criteria
Define what "best" means for your use case:
```bash
# Focus on composition
find-best-images --criteria composition --weight 0.8

# Balance multiple factors
find-best-images --criteria quality,composition,aesthetics --weights 0.4,0.3,0.3

# Custom scoring function
find-best-images --scorer custom_scorer.py
```

### Multiple Output Formats
- **Copy files** - Copy best images to output directory
- **Create lists** - Generate text/CSV list of best images
- **Generate reports** - HTML report with scores and thumbnails
- **Symlinks** - Link to originals without copying

### Preview Mode
Review AI selections before committing:
```bash
# Preview without copying
find-best-images --dir ./images --top 50 --preview

# Interactive review
find-best-images --dir ./images --top 50 --interactive
```

### Fast Processing
Optimized for large image collections:
- Efficient AI model loading
- Batch inference
- GPU acceleration (if available)
- Intelligent caching

---

## Use Cases

### Post-Generation Curation
Filter thousands of AI generations:
```bash
# Generate 500 images
comfyui-batch --count 500

# Find top 20
find-best-images --dir outputs/ --top 20 --output curated/
```

### Dataset Preparation
Find quality training images:
```bash
# Curate training dataset
find-best-images --dir raw_images/ --top 1000 \
  --criteria quality,composition \
  --output training_dataset/
```

### Portfolio Selection
Choose your best work:
```bash
# Find top 10 for portfolio
find-best-images --dir portfolio_candidates/ --top 10 \
  --criteria composition,aesthetics \
  --output portfolio/
```

### Quality Control
Identify problematic generations:
```bash
# Find worst images (for analysis)
find-best-images --dir outputs/ --bottom 10 --output review/

# Flag low-quality images
find-best-images --dir outputs/ --threshold 0.5 --flag-below
```

### Batch Validation
Ensure generation quality at scale:
```bash
# Analyze quality distribution
find-best-images --dir batch_outputs/ --report quality_report.html

# Filter by minimum quality
find-best-images --dir batch_outputs/ --min-score 0.7 --output passed/
```

---

## Installation

```bash
# PyPI (coming soon)
pip install find-best-images

# From source
git clone https://github.com/djdarcy/find-best-images
cd find-best-images
pip install -e ".[dev]"
```

---

## Usage

### Basic Usage

```bash
# Find top 10 images
find-best-images --dir ./images --top 10 --output ./best

# Find top 5% of images
find-best-images --dir ./images --top-percent 5 --output ./best

# Use specific criteria
find-best-images --dir ./images --top 20 \
  --criteria composition,sharpness \
  --output ./best
```

### Advanced Usage

```bash
# Preview before committing
find-best-images --dir ./images --top 10 --preview

# Interactive selection
find-best-images --dir ./images --top 20 --interactive

# Generate HTML report
find-best-images --dir ./images --report report.html

# Custom weights
find-best-images --dir ./images --top 10 \
  --criteria quality,composition,aesthetics \
  --weights 0.5,0.3,0.2 \
  --output ./best
```

---

## Example Workflow

```bash
# 1. Generate large batch
comfyui-batch-generate --count 500

# 2. Find top 50 images
find-best-images --dir outputs/ --top 50 \
  --criteria quality,composition \
  --output curated/

# 3. Review interactively
find-best-images --dir curated/ --interactive

# 4. Organize by quality score
pattern-break rename --dir curated/ \
  --template "{quality_score}_{filename}.png"
```

---

## AI Models

find-best-images uses AI models for quality assessment:

### Default Model
- **Auto-downloaded** on first run
- **Size**: ~100MB
- **Speed**: ~10-50 images/second (GPU)
- **Accuracy**: Trained on diverse image datasets

### Custom Models
```bash
# Use custom quality model
find-best-images --model path/to/model.pth

# Use different criteria models
find-best-images --composition-model comp_model.pth \
                 --sharpness-model sharp_model.pth
```

---

## Technical Requirements

- Python 3.10+
- AI model for quality analysis (auto-downloaded)
- Adequate RAM for batch processing (8GB+ recommended)
- Optional: GPU for faster processing

---

## Performance

### Processing Speed

| Hardware | Images/Second |
|----------|---------------|
| CPU (8-core) | ~5 images/sec |
| GPU (RTX 3060) | ~30 images/sec |
| GPU (RTX 4090) | ~80 images/sec |

### Memory Usage

| Batch Size | RAM Usage |
|------------|-----------|
| 100 images | ~2GB |
| 1,000 images | ~4GB |
| 10,000 images | ~8GB |

---

## License

GPL 3.0 - See repository for details

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**

# DazzleML Use Cases

**Who should use DazzleML and how**

---

## Overview

DazzleML provides AI development tools for different audiences. Find your use case below to see which tools are right for you.

---

## 🎨 AI Artists

**You create images, videos, or other AI-generated content.**

### What You Need

- **One-click optimizations** - No technical setup
- **Quality curation** - Find best outputs quickly
- **Fast workflows** - Spend time creating, not waiting
- **Reliable tools** - Works every time

### DazzleML Tools for Artists

**[ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)**:
- One-click installation of performance optimizations
- 20-40% faster image generation
- Lower VRAM usage
- No manual compilation needed

**[find-best-images](projects/find-best-images.md)**:
- Find your best images with AI-powered curation
- Analyze thousands of generations in seconds
- Customizable quality criteria
- Export top selections automatically

**Workflow Optimization**:
- Monitor training progress for custom models
- Optimize generation workflows
- Batch process at scale

### Example Workflow

```bash
# 1. Optimize ComfyUI
cd comfyui-triton-sageattention-installer
python install.py

# 2. Generate batch
# (Use ComfyUI with 20-40% speed boost)

# 3. Find best images
find-best-images --dir outputs/ --top 20 --output portfolio/
```

---

## 👨‍💻 AI Developers

**You build applications with AI or train custom models.**

### What You Need

- **Integration tools** - Connect AI to your systems
- **Monitoring** - Track training and generation
- **Organization** - Manage datasets and models
- **Performance** - Optimize AI workflows

### DazzleML Tools for Developers

**[MCP Integrations](projects/mcp-integrations.md)**:
- Integrate AI assistants into dev workflows
- Build custom AI tools with MCP
- Task management integration
- Secure AI access to your systems

**[AI Training Monitor](projects/ai-training-monitor.md)**:
- Real-time training visualization
- Track loss, learning rate, samples
- Monitor GPU resources
- Compare experiments

**[ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)**:
- Performance optimization for production
- Automated installation and configuration
- Verified optimizations

**Integration with [DazzleLib](https://github.com/DazzleLib)**:
- File operations for datasets
- Hash verification for data integrity
- Cross-platform utilities

### Example Workflow

```bash
# 1. Prepare dataset
# (Use DazzleLib for file operations)

# 2. Start training with monitoring
python train.py --monitor localhost:8080

# 3. Watch in browser
http://localhost:8080/training/current

# 4. Use MCP for AI-assisted development
# (AI can query training status, manage tasks)
```

---

## 🎓 AI Researchers

**You experiment with models, techniques, and datasets.**

### What You Need

- **Experiment tracking** - Compare training runs
- **Dataset tools** - Curate and validate data
- **Reproducibility** - Document and share setups
- **Performance** - Benchmark optimizations

### DazzleML Tools for Researchers

**[AI Training Monitor](projects/ai-training-monitor.md)**:
- Track multiple experiments
- Compare hyperparameters
- Export training reports
- Document experiment progress

**[find-best-images](projects/find-best-images.md)**:
- Dataset curation and validation
- Quality assessment at scale
- Identify problematic samples
- Prepare training data

**[ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)**:
- Benchmark performance improvements
- Test optimization techniques
- Reproducible environment setup

**MCP Tools**:
- Build custom research tools
- Integrate with existing workflows
- Automate repetitive tasks

### Example Workflow

```bash
# 1. Curate dataset
find-best-images --dir raw_data/ --top 5000 \
  --criteria quality,composition \
  --output training_set/

# 2. Run experiments with monitoring
for lr in 0.001 0.0001 0.00001; do
  python train.py --lr $lr --monitor localhost:8080 &
done

# 3. Compare results
ai-training-monitor compare exp1 exp2 exp3

# 4. Generate report
ai-training-monitor report --runs exp1,exp2,exp3 \
  --output paper_figures/
```

---

## 💼 Content Studios

**You create AI content at scale for clients or products.**

### What You Need

- **Batch processing** - Handle thousands of images
- **Quality control** - Ensure consistent output
- **Team workflows** - Collaborate efficiently
- **Production monitoring** - Track generation services

### DazzleML Tools for Studios

**[find-best-images](projects/find-best-images.md)**:
- Batch image curation at scale
- Quality control automation
- Client delivery selection
- Brand consistency checking

**[ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)**:
- Production optimization
- Faster client turnaround
- Lower infrastructure costs
- Reliable performance

**Training Tools**:
- Train custom models for brand consistency
- Monitor training progress
- Production deployment

**Workflow Integration**:
- Automated workflows with [DazzleTools](https://github.com/DazzleTools)
- File management with pattern-break
- Batch operations

### Example Workflow

```bash
# 1. Client brief: Generate 500 product images

# 2. Optimize generation
cd comfyui-triton-sageattention-installer
python install.py

# 3. Generate batch
# (ComfyUI workflows optimized for speed)

# 4. Quality control
find-best-images --dir client_batch/ --min-score 0.7 \
  --output qc_passed/

# 5. Curate client delivery
find-best-images --dir qc_passed/ --top 50 \
  --criteria composition,brand_fit \
  --output client_delivery/

# 6. Organize for delivery
pattern-break rename --dir client_delivery/ \
  --template "client_project_{date}_{count}.png"
```

---

## Choosing the Right Tools

### Quick Decision Tree

**Question 1**: What do you primarily do?
- **Generate AI content** → Start with [ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)
- **Train models** → Start with [AI Training Monitor](projects/ai-training-monitor.md)
- **Curate large collections** → Start with [find-best-images](projects/find-best-images.md)
- **Build AI integrations** → Start with [MCP Integrations](projects/mcp-integrations.md)

**Question 2**: What's your biggest pain point?
- **Slow generation** → ComfyUI Triton Installer
- **Finding good outputs** → find-best-images
- **Tracking training** → AI Training Monitor
- **Manual workflows** → MCP Integrations + DazzleTools

**Question 3**: What's your technical level?
- **Artist (non-technical)** → ComfyUI Triton Installer + find-best-images
- **Developer** → All tools + MCP integration
- **Researcher** → Training Monitor + find-best-images + MCP
- **Studio** → All tools for production workflows

---

## Getting Started

### For Artists

1. Install [ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md) first
2. Generate images with speed boost
3. Add [find-best-images](projects/find-best-images.md) for curation

### For Developers

1. Start with [MCP Server Tutorial](projects/mcp-integrations.md)
2. Add [AI Training Monitor](projects/ai-training-monitor.md) if training
3. Integrate with [DazzleLib](https://github.com/DazzleLib) for utilities

### For Researchers

1. Set up [AI Training Monitor](projects/ai-training-monitor.md)
2. Use [find-best-images](projects/find-best-images.md) for datasets
3. Benchmark with [ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)

### For Studios

1. Optimize with [ComfyUI Triton Installer](projects/comfyui-triton-sageattention-installer.md)
2. Automate curation with [find-best-images](projects/find-best-images.md)
3. Add [DazzleTools](https://github.com/DazzleTools) for file management

---

## Community Examples

### Real Workflows from Users

*Coming soon: User-submitted workflows and case studies*

Share your workflow:
- [GitHub Discussions](https://github.com/DazzleML/discussions)
- Tag `#DazzleML` on social media
- Contribute to documentation

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**

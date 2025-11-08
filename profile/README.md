# DazzleML

**AI Development Tools and Integration Ecosystem**

[![GitHub](https://img.shields.io/badge/GitHub-DazzleML-blue?logo=github)](https://github.com/DazzleML)
[![License: GPL 3.0](https://img.shields.io/badge/License-GPL%203.0-green.svg)](LICENSE)
[![Sponsor](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?logo=github-sponsors)](https://github.com/sponsors/djdarcy)

> Tools for AI-assisted development, image generation workflows, training monitoring, and intelligent task management. From ComfyUI optimization to AI-powered file curation.

---

## What is DazzleML?

**DazzleML** brings together tools for working with AI systems - whether you're generating images, training models, organizing datasets, or building AI-integrated workflows. These tools emerged from real AI development work and solve actual problems encountered in production environments.

### Philosophy

- **Practical AI Integration** - Tools for working with AI, not just talking about it
- **Lower the Barriers** - Make advanced AI features accessible with one click
- **Monitor Everything** - Visibility into training, generation, and processing
- **Intelligence in Workflows** - AI assistance where it makes sense
- **Production Ready** - Tools tested in real development environments

---

## Who Should Use DazzleML?

### 🎨 AI Artists
- One-click installation of ComfyUI performance optimizations
- Find your best images with AI-powered curation
- Monitor training progress for custom models
- Optimize generation workflows

### 👨‍💻 AI Developers
- MCP integration for AI assistant workflows
- Training monitoring and visualization
- Dataset organization and management
- Performance optimization tools

### 🎓 AI Researchers
- Training experiment tracking
- Dataset curation and validation
- Reproducible environment setup
- Performance benchmarking tools

### 💼 Content Studios
- Batch image curation at scale
- Training custom models for brand consistency
- Automated workflow optimization
- Production monitoring tools

---

## Featured Projects

### 🌟 Most Popular: ComfyUI Triton & SageAttention Installer

**[GitHub](https://github.com/djdarcy/comfyui-triton-and-sageattention-installer) | Status: Active**

One-click installation of Triton and SageAttention optimizations for ComfyUI. Get significant speed improvements without manual compilation or environment setup.

**Before:**
```
1. Install CUDA toolkit manually
2. Set up build environment
3. Clone Triton repository
4. Compile Triton from source (pray it works)
5. Install SageAttention dependencies
6. Configure ComfyUI paths
7. Debug inevitable errors
8. Hours of troubleshooting
```

**After:**
```
python install.py
(Everything installs automatically, works first try)
```

**Features**:
- **Automatic installation** - No manual compilation needed
- **Environment detection** - Automatically finds ComfyUI and Python
- **Dependency management** - Handles all prerequisites
- **Verification** - Tests installation before finishing
- **Rollback support** - Safe to undo if needed
- **Cross-platform** - Windows, Linux (macOS coming soon)

**Performance Improvements**:
- **Faster generation**: 20-40% speed improvement in many workflows
- **Lower memory**: Better VRAM utilization
- **Stable diffusion**: Optimized attention mechanisms
- **Production ready**: Tested with various models and workflows

**Use Cases**:
- Speed up ComfyUI image generation
- Reduce VRAM usage for larger models
- Optimize batch processing workflows
- Enable advanced attention mechanisms
- Test performance optimizations safely

**Status**: Most downloaded Dazzle project overall. Actively maintained with updates for new ComfyUI versions.

---

### 🎯 find-best-images

**[GitHub](https://github.com/djdarcy/find-best-images) | Status: Active**

AI-powered image curation tool. Find the best images from large collections using AI analysis of composition, quality, and aesthetics.

**The Problem**:
You generate 1,000 images. Which 10 are worth keeping? Manual review takes hours.

**The Solution**:
```bash
find-best-images --dir ./generations --top 10 --output best/
# AI analyzes all images, exports top 10 to best/
```

**Features**:
- **AI quality analysis** - Composition, sharpness, aesthetics
- **Batch processing** - Analyze thousands of images
- **Customizable criteria** - Define what "best" means for your use case
- **Multiple output formats** - Copy files, create lists, generate reports
- **Preview mode** - Review AI selections before committing
- **Fast processing** - Optimized for large image collections

**Use Cases**:
- **Post-generation curation**: Filter thousands of AI generations
- **Dataset preparation**: Find quality training images
- **Portfolio selection**: Choose your best work
- **Quality control**: Identify problematic generations
- **Batch validation**: Ensure generation quality at scale

**Example Workflow**:
```bash
# Generate 500 variations
comfyui-batch-generate --count 500

# Find top 20 best images
find-best-images --dir outputs/ --top 20 --output curated/

# Review and refine
find-best-images --dir curated/ --interactive
```

---

### 📊 AI Training Monitor

**[GitHub](https://github.com/DazzleML/ai-training-monitor) | Status: Active**

Monitor and visualize AI model training in real-time. Track loss, learning rate, sample outputs, and system resources.

**Features**:
- **Real-time monitoring** - Watch training progress live
- **Loss visualization** - Plot training and validation loss
- **Sample tracking** - View generated samples during training
- **Resource monitoring** - GPU utilization, memory, temperature
- **Experiment comparison** - Compare multiple training runs
- **Export reports** - Generate training summaries

**Use Cases**:
- Monitor long training runs remotely
- Catch overfitting early
- Compare hyperparameter experiments
- Debug training issues
- Generate training reports for documentation

**Example**:
```bash
# Start training with monitoring
python train.py --monitor localhost:8080

# View in browser
http://localhost:8080/training/experiment-123
```

---

### 🤖 MCP Server Integrations

**Model Context Protocol (MCP) Tools**

Tools for integrating AI assistants into development workflows using the Model Context Protocol.

#### MCP Server Tutorial

**[GitHub](https://github.com/DazzleML/MCP-Server-Tutorial) | Status: Active**

Complete guide to building MCP servers for AI assistant integration. Examples include:

- File system access for AI assistants
- Task management integration (Todoist)
- Database query interfaces
- Custom tool creation
- Security best practices

**Use Cases**:
- Build custom AI assistant tools
- Integrate AI into existing systems
- Create domain-specific AI capabilities
- Learn MCP architecture

#### Integration with TodoAI

DazzleML tools integrate with the [TodoAI](https://github.com/Todo-AI) ecosystem:

- **TodoAI-Todoist**: MCP server with AI capabilities for task management
- AI-powered task prioritization and scheduling
- Natural language task creation
- Intelligent task completion suggestions

---

### 🎨 Pattern-Break Integration

**[GitHub](https://github.com/DazzleTools/pattern-break) | Cross-organization tool**

While primarily in DazzleTools, pattern-break works excellently with DazzleML for:

- **Dataset organization**: Rename training images by patterns
- **Batch file operations**: Prepare datasets for training
- **Metadata extraction**: Parse filenames for training tags
- **Template processing**: Generate training configurations

**Example with AI workflows**:
```bash
# Organize training dataset
pattern-break rename --pattern "raw_*.png" \
  --template "training/category_{hash}_{count}.png"

# Extract tags from filenames
pattern-break extract --pattern "*_tags_*.jpg" \
  --output tags.csv
```

---

## Installation

### Individual Tools

Each tool has its own installation method:

```bash
# ComfyUI Triton Installer
cd comfyui-triton-and-sageattention-installer
python install.py

# find-best-images
pip install find-best-images  # (coming to PyPI)

# AI Training Monitor
pip install ai-training-monitor  # (coming to PyPI)

# MCP integrations
pip install todoai-todoist  # (coming to PyPI)
```

### Development Installation

```bash
# Clone and install in development mode
git clone https://github.com/DazzleML/<tool-name>
cd <tool-name>
pip install -e ".[dev]"
```

---

## Tool Categories

### By Function

| Category | Tools |
|----------|-------|
| **Performance Optimization** | ComfyUI Triton Installer |
| **Image Curation** | find-best-images |
| **Training Tools** | AI Training Monitor |
| **AI Integration** | MCP Server Tutorial, TodoAI integrations |
| **Workflow Automation** | Pattern-break (cross-org) |

### By AI Domain

| Domain | Tools |
|--------|-------|
| **Image Generation** | ComfyUI Triton Installer, find-best-images |
| **Model Training** | AI Training Monitor |
| **Task Management** | TodoAI integrations |
| **Development** | MCP Server Tutorial |

---

## Common Workflows

### 1. Optimize ComfyUI for Production

```bash
# Install performance optimizations
cd comfyui-triton-and-sageattention-installer
python install.py

# Verify installation
python verify.py

# Generate with optimizations
# (ComfyUI automatically uses Triton/SageAttention)
```

### 2. Large-Scale Image Generation and Curation

```bash
# Generate large batch
comfyui-batch --workflow portrait.json --count 1000

# Curate best results
find-best-images --dir outputs/ --top 50 --criteria quality,composition

# Organize keepers
pattern-break rename --pattern "outputs/*.png" \
  --template "curated/{date}_{quality_score}.png"
```

### 3. Model Training with Monitoring

```bash
# Start training with monitoring
python train.py --monitor localhost:8080 \
  --checkpoint-interval 100

# Watch in browser
http://localhost:8080/training/current

# Compare experiments
ai-training-monitor compare exp1 exp2 exp3
```

### 4. AI-Assisted Task Management

```bash
# Start TodoAI MCP server
todoai-todoist-server --port 3000

# Connect AI assistant
# (Assistant can now create, query, and manage tasks)

# AI analyzes task patterns
todoai-analyze --project "AI Research"
```

---

## Integration with DazzleProj Ecosystem

DazzleML works seamlessly with other Dazzle organizations:

### With DazzleLib

```python
from dazzle_filekit import calculate_file_hash, copy_file

# Verify training dataset integrity
for image_file in training_images:
    hash_value = calculate_file_hash(image_file)
    verify_dataset_hash(hash_value)
```

### With DazzleTools

```bash
# Use preserve to backup training data
preserve COPY --src ./training-data --dst ./backups/training-2025-11-07

# Use listall to catalog dataset
listall ./training-data > dataset-manifest.txt

# Use dazzlesum to verify dataset
dazzlesum calculate ./training-data --algorithm sha256
```

### With DazzleNodes

- **ComfyUI workflows** optimized with Triton installer
- **Image curation** feeds into ComfyUI generation
- **Training monitoring** for custom node models

---

## Development Roadmap

### Current Projects (Available Now)

- ✅ **ComfyUI Triton Installer** - Most popular Dazzle project
- ✅ **find-best-images** - AI-powered image curation
- ✅ **AI Training Monitor** - Training visualization
- ✅ **MCP Server Tutorial** - AI assistant integration guide

### Planned Projects

**Q4 2025 - Q1 2026**:
- **Model version manager** - Track and manage model versions
- **Dataset analyzer** - Statistical analysis of training datasets
- **Generation optimizer** - Automatic workflow optimization
- **Training scheduler** - Intelligent training job scheduling

**Q2-Q3 2026**:
- **Multi-GPU training orchestrator** - Distributed training management
- **Model comparison tool** - Compare model outputs systematically
- **Automated dataset curation** - AI-powered dataset quality control
- **Production monitoring dashboard** - Monitor generation services

**Long Term**:
- **Hosted training service** - Cloud training with monitoring
- **Model marketplace integration** - Share and discover models
- **Enterprise features** - Team collaboration, access control
- **Advanced AI integrations** - More MCP servers and tools

*Roadmap prioritized based on community feedback and sponsorship support.*

---

## Platform Support

| Tool | Windows | Linux | macOS |
|------|---------|-------|-------|
| ComfyUI Triton Installer | ✅ Full | ✅ Full | 🚧 Coming Soon |
| find-best-images | ✅ Full | ✅ Full | ✅ Full |
| AI Training Monitor | ✅ Full | ✅ Full | ✅ Full |
| MCP Server Tutorial | ✅ Full | ✅ Full | ✅ Full |
| TodoAI integrations | ✅ Full | ✅ Full | ✅ Full |

---

## Contributing

Contributions welcome! Each tool has its own repository and contribution guidelines.

### Development Process

1. Fork the tool repository
2. Create a feature branch
3. Make your changes with tests
4. Ensure cross-platform compatibility
5. Test with real AI workloads
6. Submit a pull request

### Code Quality Standards

- **AI integration testing** - Test with actual models and workflows
- **Performance validation** - Benchmark improvements
- **Cross-platform** - Test on Windows, Linux, macOS
- **Documentation** - Examples and use cases
- **Type hints** - For maintainability

---

## 💰 Sustainability

**DazzleML** is part of the [DazzleProj](https://github.com/DazzleProj) ecosystem.

**Current sponsorship: $0/month | Goal: $1,000/month**

### Why Sponsor DazzleML?

AI tools require significant development effort:
- Testing across different models and hardware
- Keeping up with rapid AI ecosystem changes
- Supporting multiple platforms and versions
- Maintaining performance optimizations
- Building integration layers

**If you use DazzleML tools professionally:**

**Example: ComfyUI Triton Installer**
- Time saved vs manual setup: **4-6 hours**
- Ongoing maintenance saved: **2 hours/month**
- Your hourly rate: $75-150
- One-time value: **$300-900**
- Monthly value: **$150-300**

Contributing $25-50/month helps ensure continued development and support.

### How to Help

1. 💵 **[Sponsor on GitHub](https://github.com/sponsors/djdarcy)** - Direct support
2. ⭐ **Star repositories** - Increases visibility in AI community
3. 💬 **Share your workflows** - Help others learn
4. 📝 **Write tutorials** - Document your AI workflows
5. 🔧 **Contribute tools** - Build AI tools for everyone

### Sponsor Benefits

- 🌟 **$5/month** - Supporter: Name in README
- 🌟🌟 **$25/month** - Contributor: Logo on DazzleProj.com
- 🌟🌟🌟 **$100/month** - Bronze Sponsor: Priority issue handling
- 🌟🌟🌟🌟 **$500/month** - Silver Sponsor: Influence roadmap
- 🌟🌟🌟🌟🌟 **$2,000/month** - Gold Sponsor: Custom tool development

---

## Documentation

- **Tool Documentation**: See individual repository READMEs
- **Integration Guides**: MCP Server Tutorial repository
- **Example Workflows**: `examples/` directories
- **Video Tutorials**: Coming based on sponsorship
- **API Documentation**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*

---

## Related Projects

### Part of DazzleProj Ecosystem

- **[DazzleProj](https://github.com/DazzleProj)** - Ecosystem coordination
- **[DazzleLib](https://github.com/DazzleLib)** - Foundation libraries
- **[DazzleTools](https://github.com/DazzleTools)** - Command-line tools
- **[DazzleNodes](https://github.com/DazzleNodes)** - ComfyUI custom nodes
- **[DazzleML](https://github.com/DazzleML)** - AI development tools ← *You are here*

### Related AI Ecosystems

- **[TodoAI](https://github.com/Todo-AI)** - Task-based OS with AI integration
  - TodoAI-Todoist: Enhanced MCP server with local caching
  - TodoAI-Todoist-Notepad: Flutter app with natural syntax
- **[ComfyUI](https://github.com/comfyanonymous/ComfyUI)** - Node-based UI for Stable Diffusion
- **[Model Context Protocol](https://modelcontextprotocol.io)** - AI assistant integration standard

---

## Community

- **GitHub Discussions**: [AI Tools Discussion](https://github.com/DazzleML/discussions)
- **ComfyUI Community**: Share optimized workflows
- **AI Development**: Collaborate on integrations
- **Training Tips**: Share monitoring insights

---

## Technical Requirements

### General Requirements

- Python 3.10+ (for most tools)
- Compatible with Windows, Linux, macOS
- Adequate disk space for datasets/models

### ComfyUI Triton Installer

- CUDA-capable GPU (NVIDIA)
- CUDA Toolkit 11.8+ or 12.1+
- ComfyUI installation
- 10GB free disk space

### AI Training Monitor

- Python 3.10+
- Web browser for visualization
- Training framework (PyTorch, TensorFlow, etc.)

### find-best-images

- Python 3.10+
- AI model for quality analysis (auto-downloaded)
- Adequate RAM for batch processing

---

## Acknowledgments

Built with inspiration from:
- Real AI development workflows and pain points
- ComfyUI community's innovative approaches
- Open-source AI training tools and research
- Production AI deployment experiences
- Model Context Protocol community

---

## License

DazzleML projects use **GPL 3.0** to encourage open AI tooling and ensure improvements benefit everyone.

See individual project repositories for specific licensing information.

---

## Contact

- **GitHub**: [@djdarcy](https://github.com/djdarcy)
- **Issues**: Use repository-specific issue trackers
- **Discussions**: [GitHub Discussions](https://github.com/DazzleML/discussions)
- **Sponsorship**: [GitHub Sponsors](https://github.com/sponsors/djdarcy)
- **Website**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*

---

**Built by someone who trains models and generates images every day** 🤖

*AI tools for real work, not just demos.*

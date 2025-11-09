# DazzleML

**AI Development Tools and Integration Ecosystem**

[![GitHub](https://img.shields.io/badge/GitHub-DazzleML-blue?logo=github)](https://github.com/DazzleML)
[![License: GPL 3.0](https://img.shields.io/badge/License-GPL%203.0-green.svg)](LICENSE)
[![Sponsor](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?logo=github-sponsors)](https://github.com/sponsors/djdarcy)

> Tools for AI-assisted development, image generation workflows, training monitoring, and intelligent task management. From ComfyUI optimization to AI-powered file curation.

---

## What is DazzleML?

**DazzleML** brings together tools for working with AI systems - whether you're generating images, training models, organizing datasets, or building AI-integrated workflows. These tools emerged from real AI development work and solve actual problems encountered in production environments.

**[Read our philosophy →](../docs/philosophy.md)** | **[See who should use DazzleML →](../docs/use-cases.md)**

---

## Featured Projects

### 🌟 [ComfyUI Triton & SageAttention Installer](https://github.com/djdarcy/comfyui-triton-and-sageattention-installer)
**Most Popular Dazzle Project Overall**

One-click installation of Triton and SageAttention optimizations for ComfyUI. Get 20-40% speed improvements without manual compilation.

```bash
python install.py  # Everything installs automatically
```

**[Full documentation →](../docs/projects/comfyui-triton-sageattention-installer.md)** | **Status: Active**

---

### 🎯 [find-best-images](https://github.com/djdarcy/find-best-images)

AI-powered image curation tool. Find the best images from large collections using AI analysis of composition, quality, and aesthetics.

```bash
find-best-images --dir ./generations --top 10 --output best/
```

**[Full documentation →](../docs/projects/find-best-images.md)** | **Status: Active**

---

### 📊 [AI Training Monitor](https://github.com/DazzleML/ai-training-monitor)

Monitor and visualize AI model training in real-time. Track loss, learning rate, sample outputs, and system resources.

```bash
python train.py --monitor localhost:8080
# View at http://localhost:8080
```

**[Full documentation →](../docs/projects/ai-training-monitor.md)** | **Status: Active**

---

### 🤖 [MCP Server Integrations](https://github.com/DazzleML/MCP-Server-Tutorial)

Tools for integrating AI assistants into development workflows using the Model Context Protocol. Includes TodoAI integration.

**[Full documentation →](../docs/projects/mcp-integrations.md)** | **Status: Active**

---

## Quick Start

```bash
# 1. Optimize ComfyUI for faster generation
cd comfyui-triton-and-sageattention-installer
python install.py

# 2. Generate images (now 20-40% faster)
# Use ComfyUI normally

# 3. Find best images from your outputs
find-best-images --dir outputs/ --top 20 --output best/

# 4. Monitor training runs
python train.py --monitor localhost:8080
```

---

## Documentation

- **[Who Should Use DazzleML](../docs/use-cases.md)** - Artists, developers, researchers, studios
- **[Philosophy](../docs/philosophy.md)** - Design principles and approach
- **[Roadmap](../docs/roadmap.md)** - Current status and planned features
- **[Sustainability](../docs/sustainability.md)** - Supporting development

**Project Documentation**:
- **[ComfyUI Triton Installer](../docs/projects/comfyui-triton-sageattention-installer.md)**
- **[find-best-images](../docs/projects/find-best-images.md)**
- **[AI Training Monitor](../docs/projects/ai-training-monitor.md)**
- **[MCP Integrations](../docs/projects/mcp-integrations.md)**

---

## Integration with DazzleProj Ecosystem

DazzleML works seamlessly with other Dazzle organizations:

**[DazzleLib](https://github.com/DazzleLib)** - Use dazzle-filekit for dataset verification and file operations

**[DazzleTools](https://github.com/DazzleTools)** - Use preserve for training data backups, pattern-break for dataset organization

**[DazzleNodes](https://github.com/DazzleNodes)** - ComfyUI custom nodes optimized with Triton installer

---

## Platform Support

| Tool | Windows | Linux | macOS |
|------|---------|-------|-------|
| ComfyUI Triton Installer | ✅ Full | ✅ Full | 🚧 Coming |
| find-best-images | ✅ Full | ✅ Full | ✅ Full |
| AI Training Monitor | ✅ Full | ✅ Full | ✅ Full |
| MCP Server Tutorial | ✅ Full | ✅ Full | ✅ Full |

---

## Contributing

Contributions welcome! Each tool has its own repository with contribution guidelines.

**General Process**:
1. Fork the tool repository
2. Create a feature branch
3. Test with real AI workloads
4. Ensure cross-platform compatibility
5. Submit a pull request

**[Read contributing guidelines →](CONTRIBUTING.md)**

---

## 💰 Sustainability

**[Learn about supporting DazzleML →](../docs/sustainability.md)**

If DazzleML saves you time, consider **[sponsoring on GitHub](https://github.com/sponsors/djdarcy)** or **[buying us a coffee](https://www.buymeacoffee.com/djdarcy)**

**Current sponsorship**: $0/month | **Goal**: $1,000/month

---

## Part of DazzleProj

DazzleML is one of five organizations in the Dazzle ecosystem:

- **[DazzleProj](https://github.com/DazzleProj)** - Ecosystem coordination
- **[DazzleLib](https://github.com/DazzleLib)** - Foundation libraries
- **[DazzleTools](https://github.com/DazzleTools)** - Command-line tools
- **[DazzleNodes](https://github.com/DazzleNodes)** - ComfyUI custom nodes
- **[DazzleML](https://github.com/DazzleML)** - AI development tools ← *You are here*

---

## Related AI Ecosystems

- **[TodoAI](https://github.com/Todo-AI)** - Task-based OS with AI integration
- **[ComfyUI](https://github.com/comfyanonymous/ComfyUI)** - Node-based UI for Stable Diffusion
- **[Model Context Protocol](https://modelcontextprotocol.io)** - AI assistant integration standard

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

# ComfyUI Triton & SageAttention Installer

**One-click installation of Triton and SageAttention optimizations for ComfyUI**

**[GitHub Repository](https://github.com/djdarcy/comfyui-triton-and-sageattention-installer)** | **Status: Active**

> **Most Popular Dazzle Project**: Simplifies GPU-accelerated inference setup for Windows users with automated dependency management and RTX 5090 support.

---

## The Problem

Installing SageAttention on Windows has been notoriously difficult due to compilation issues, missing dependencies, and platform-specific challenges:

```
1. Install CUDA toolkit manually
2. Set up Visual Studio Build Tools
3. Find correct pre-built wheels for your PyTorch/CUDA/Python combo
4. Download Python development headers
5. Compile from source if no wheels available
6. Debug inevitable errors
7. Hours of troubleshooting
```

Manual compilation is error-prone, platform-specific, and time-consuming.

---

## The Solution

```bash
python comfyui_triton_sageattention.py --install --with-custom-nodes --backup
```

One command handles everything — CUDA detection, dependency installation, pre-built wheel selection, and environment backup.

---

## Features

### Automated Installation
- **No manual compilation** — Pre-built wheels or automatic building
- **Automatic CUDA detection** — Detects your GPU and CUDA version
- **Python header management** — Automatically sets up development headers
- **Visual Studio automation** — Handles Build Tools installation if needed
- **Pre-built wheel support** — Uses pre-compiled wheels to avoid build issues

### Discovery & Detection
```bash
# Find all ComfyUI installations on your system
python comfyui_triton_sageattention.py --show-installed locations

# Install with interactive discovery
python comfyui_triton_sageattention.py --install discover

# Check what's currently installed
python comfyui_triton_sageattention.py --show-installed
```

### Environment Backup & Restore
```bash
# Create backup before changes
python comfyui_triton_sageattention.py --backup

# List available backups
python comfyui_triton_sageattention.py --backup list

# Restore from backup
python comfyui_triton_sageattention.py --backup-restore 1

# Clean up old backups
python comfyui_triton_sageattention.py --backup-clean --keep-latest 1
```

### SageAttention Version Control
```bash
# Install SageAttention 1 (~2.1x speedup) or 2 (~3x speedup)
python comfyui_triton_sageattention.py --install --sage-version 1  # or 2

# Upgrade existing installation
python comfyui_triton_sageattention.py --upgrade

# Opt-in to experimental/prerelease versions
python comfyui_triton_sageattention.py --install --experimental
```

### Cross-Platform Support
- **Windows** — ✅ Full support (primary target)
- **Linux** — ✅ Full support
- **macOS** — 🚧 Experimental stubs

### Dry Run Mode
```bash
# Preview what would be installed without making changes
python comfyui_triton_sageattention.py --install --dryrun
```

---

## What Gets Installed

1. **PyTorch** with CUDA support matching your GPU
2. **Triton-Windows** — OpenAI's Triton for Windows
3. **SageAttention** — Efficient attention mechanism (2.x preferred, falls back to 1.x)
4. **Python Development Files** — Required headers and libs

With `--with-custom-nodes`:

5. **ComfyUI-VideoHelperSuite** — Video encoding/decoding utilities
6. **DazzleNodes** — DazzleML node collection

---

## Use Cases

### Speed Up Image Generation
Triton and SageAttention optimize attention mechanisms for faster inference:
- SageAttention 1: ~2.1x speedup vs FlashAttention2
- SageAttention 2: ~3x speedup vs FlashAttention2

### ComfyUI Portable Support
Works with pre-packaged ComfyUI distributions that use `python_embeded`:
```bash
cd C:\ComfyUI_windows_portable
python path\to\comfyui_triton_sageattention.py --install
```

### RTX 5090 / Blackwell Support
Full support for RTX 5090 with CUDA 12.8. Also includes a separate installer for Ostris AI Toolkit users:
```bash
python ai_toolkit_rtx5090_installer.py --non-interactive
```

### Safe Performance Testing
Test optimizations with easy rollback via the backup system:
```bash
python comfyui_triton_sageattention.py --install --backup
# Test your workflows...
python comfyui_triton_sageattention.py --backup-restore 1  # Rollback if needed
```

---

## Installation

### Prerequisites

- Windows 10/11 (Linux supported, macOS experimental)
- NVIDIA GPU with CUDA support
- Existing ComfyUI installation
- Python 3.8+ (or ComfyUI portable's embedded Python)

### Quick Install

```bash
# Run from your ComfyUI directory, or use --base-path
python comfyui_triton_sageattention.py --install --with-custom-nodes --backup
```

### Command Reference

| Option | Description |
|--------|-------------|
| `--install` | Install Triton + SageAttention (use `discover` to find ComfyUI) |
| `--upgrade` | Upgrade existing SageAttention to latest compatible version |
| `--show-installed` | Show installation info (`components`, `locations`, `discover`) |
| `--cleanup` | Clean up previous installation |
| `--run` | Run ComfyUI |
| `--base-path` | ComfyUI directory path, or `discover` / `auto` |
| `--python` | Python environment: `auto`, `system`, `portable`, `venv`, or a path |
| `--sage-version` | SageAttention version: `auto`, `1`, `2`, or exact (e.g., `2.1.1`) |
| `--with-custom-nodes` | Also install VideoHelperSuite and DazzleNodes |
| `--backup` | Create environment backup before changes |
| `--backup-restore` | Restore from backup by index or timestamp |
| `--backup-clean` | Remove old backups (use with `--keep-latest N`) |
| `--dryrun` | Preview changes without installing |
| `--verbose` | Enable verbose logging |
| `--force` | Force reinstallation of all components |
| `--non-interactive` | Run without user prompts |
| `--experimental` | Allow prerelease SageAttention versions |

---

## How It Works

1. Detects platform and creates appropriate handler
2. Installs Visual Studio Build Tools (Windows, if needed)
3. Detects CUDA version for compatibility
4. Installs PyTorch with matching CUDA support
5. Installs Triton (triton-windows on Windows)
6. Downloads Python development headers
7. Installs SageAttention (pre-built wheels preferred, falls back to compilation)
8. Optionally clones custom node repositories
9. Creates launch scripts

---

## After Installation

Run ComfyUI with SageAttention enabled:

```bash
# Windows
run_nvidia_gpu.bat

# Or manually
python ComfyUI\main.py --use-sage-attention
```

---

## Troubleshooting

### SageAttention Version Check
```bash
python -m pip show sageattention
```
- Version `1.0.6` = SageAttention 1 (~2.1x speedup)
- Version `2.x.x` = SageAttention 2 (~3x speedup)

### Common Issues

**Getting SageAttention 1 instead of 2**: Your PyTorch/CUDA/Python combo may not have a pre-configured wheel. You can manually install from [woct0rdho's releases](https://github.com/woct0rdho/SageAttention/releases).

**ComfyUI not found**: Use `--base-path C:\path\to\ComfyUI` or `--install discover`.

**CUDA version mismatch**: The installer auto-detects your CUDA version. Update NVIDIA drivers if issues persist.

### Logs
Check `comfyui_install.log` for detailed information.

---

## Acknowledgments

- [woct0rdho](https://github.com/woct0rdho) — Windows wheels and triton-windows
- [thu-ml](https://github.com/thu-ml/SageAttention) — SageAttention project
- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) — The amazing UI
- [Ostris](https://github.com/ostris/ai-toolkit) — AI Toolkit for LoRA training

---

## License

MIT License — See repository for details

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**

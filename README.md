# PRISM Models Registry

Official AI model repository for the PRISM Visual Pipeline application.

## Overview

This repository contains the model registry and configuration files that tell the PRISM application which AI models are available, where to download them, and which models to recommend for different hardware configurations.

## Models Available

### Core Models (Always Required)
- **Panel Detection** (45 MB) - Comic panel layout detection and boundary identification
- **LLaVA 1.5 7B** (4.08 GB) - Large Language and Vision Assistant for visual analysis
- **LLaVA Vision Model** (624 MB) - Vision processing component for multimodal analysis

### Segmentation Models (Hardware-Dependent)
- **SAM 2 Small** (238 MB) - Efficient segmentation for CPU-only systems
- **SAM 2 Base+** (672 MB) - Balanced performance for GPU systems
- **SAM 2 Large** (1.2 GB) - Maximum quality for high-end GPU systems

## Hardware Profiles

The registry automatically recommends the optimal model configuration based on your hardware:

- **Apple Silicon** (M1/M2/M3): Base+ models optimized for Metal Performance Shaders
- **NVIDIA GPU**: Base+ models with CUDA acceleration
- **AMD GPU**: Large models with ROCm support
- **CPU Only**: Small, efficient models for systems without dedicated GPUs

## Registry Structure

### `registry.json`
The main model catalog containing:
- Model metadata (names, descriptions, sizes)
- Download URLs and checksums
- Hardware compatibility information
- Version management
- Hardware-specific recommendations

### Model Releases
Actual model files are distributed via GitHub Releases:
- Automatic global CDN distribution
- Reliable download infrastructure
- Version tracking and rollback capability

## Usage

Models are automatically downloaded by the PRISM application during first-run setup. The app:

1. Detects your hardware configuration
2. Fetches the latest registry from this repository
3. Determines optimal models for your system
4. Downloads and verifies model files
5. Stores models locally for offline operation

## Model Sources

- **LLaVA Models**: Based on [LLaVA 1.5](https://github.com/haotian-liu/LLaVA) by Haotian Liu et al.
- **SAM 2 Models**: Based on [Segment Anything Model 2](https://github.com/facebookresearch/segment-anything-2) by Meta
- **Panel Detection**: Custom trained model for comic panel detection

## Contributing

### Adding New Models
1. Add model metadata to `registry.json`
2. Upload model files to GitHub Releases
3. Update hardware profiles as needed
4. Test with PRISM application

### Model Guidelines
- Models must include SHA256 checksums
- File sizes should be optimized for target hardware
- Include comprehensive hardware compatibility information
- Follow semantic versioning for model updates

## License

Model registry and configuration files are licensed under MIT License.

Individual models may have different licenses - see model-specific documentation.

## Support

For issues with model downloads or compatibility:
- Check the [PRISM Issues](https://github.com/bd-aohk/PRISM/issues)
- Verify your hardware meets minimum requirements
- Ensure stable internet connection for downloads

---

**Total Registry Size**: ~5.4 GB (varies by hardware configuration)
**Update Frequency**: Registry checked daily, models updated as needed
**Offline Support**: Full offline operation after initial download
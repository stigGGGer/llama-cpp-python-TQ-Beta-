# llama-cpp-python + TurboQuant Fork

This repository is my custom merge of:

- `llama.cpp` from TheTom (TurboQuant branch/features)
- `llama-cpp-python` from JamesPeng

The goal of this fork is simple: run the Python version (`llama-cpp-python`) with TurboQuant support, because ready-to-use public variants were not available.

## What is included

- Integrated TurboQuant-enabled `llama.cpp` source in this project.
- Python bindings and server API from `llama-cpp-python`.
- Local wheel builds for CUDA variants (depending on build configuration).

## Why this fork exists

I needed:

- Python API compatibility (`import llama_cpp`, server mode, OpenAI-compatible endpoints)
- TurboQuant performance/quantization path from TheTom's `llama.cpp`

This fork combines both into one working build flow.

## Build notes (example)

Environment used:

- Python 3.11
- CMake
- Visual Studio Build Tools (Windows) or GCC/Clang (Linux)
- CUDA toolkit (for CUDA wheels)

Typical local build flow:

```bash
python -m pip install -U pip build wheel setuptools
pip install -r docs/requirements.txt
python -m build
```

If you build with CUDA/TurboQuant options, configure them through the same CMake/env flags you use in this repo's workflows/scripts.

## Install from local wheel

```bash
pip install dist/*.whl
```

or for platform-specific output:

```bash
pip install wheelhouse/*.whl
```

## Status

This is a personal integration fork intended for practical usage and experimentation.  
It may diverge from upstream and can require manual rebases when upstream projects change.

## Credits

Huge thanks to the original maintainers and contributors:

- `llama.cpp` community and maintainers
- TheTom for TurboQuant-related work
- JamesPeng and contributors of `llama-cpp-python`

## License

This fork follows the original project licenses.  
Please review `LICENSE.md` and upstream repositories for full licensing details.

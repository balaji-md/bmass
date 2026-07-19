# BMASS

## Bootable Model As System

**BMASS** is an experimental open-source project exploring a simple idea:

> **What if the AI model became the primary system interface instead of just another application running inside an operating system?**

BMASS boots from a USB drive into a lightweight Linux environment and automatically starts a local large language model. After installation, it operates completely offline, giving users a portable AI environment that they own and control.

---

## Why BMASS?

Most AI today is accessed through web browsers, cloud services or heavyweight desktop applications.

BMASS explores a different approach.

Instead of booting a computer and then opening an AI application, BMASS asks:

> *Can the model itself become the system?*

The operating system becomes a lightweight foundation whose primary purpose is to support the local model.

---

## Current Prototype (v0.1 Seed)

Current features include:

- Bootable Alpine Linux USB
- Offline local AI
- `llama.cpp` inference engine
- Local Qwen3 0.6B GGUF model
- Automatic BMASS launcher
- Runs on modest hardware (~4 GB RAM)

After the model has been installed, BMASS does not require an internet connection for inference.

---

## Project Goals

BMASS aims to become a portable, offline-first AI operating environment.

Future work includes:

- Safe system tools
- Model Context Protocol (MCP) integration
- Local document search
- Multiple model management
- Web interface
- Healthcare and enterprise deployments

---

## Repository Structure

```
launcher/      BMASS launcher
scripts/       Installation and setup scripts
docs/          Documentation
examples/      Example configurations
config/        Configuration files
```

---

## Philosophy

BMASS is built around five principles.

- Offline first
- User controlled
- Open source
- Lightweight
- Reproducible

---

## Current Status

This is an experimental prototype.

The objective of the first public release is simply to demonstrate that a complete AI environment can boot directly from removable media and run entirely on local hardware.

---

## Contributing

Ideas, bug reports and contributions are welcome.

This project is intended to evolve in public.

---

## License

See the LICENSE file.

# BMASS

# Bootable Model As System

> **The model is the system.**

BMASS is an open-source project exploring a different way of using artificial intelligence.

Instead of booting a computer and launching an AI application, BMASS boots directly into a lightweight Linux environment that automatically starts a local language model.

The operating system becomes a minimal foundation whose primary purpose is to support the model.

The result is a portable, offline-first AI environment that runs entirely on local hardware.

---

## Why BMASS?

Most AI today is accessed through cloud services, web browsers or desktop applications.

BMASS asks a different question:

> **Can the language model itself become the primary interface to a computer?**

Rather than adding AI to an operating system, BMASS explores making the operating system serve the AI.

The project is intentionally lightweight, transparent and reproducible.

---

# Demonstration

🎥 **Booting BMASS**

*A short demonstration video will be available here.*

(YouTube)

The demonstration shows:

- Booting directly from USB
- Automatic startup of the AI environment
- Completely offline inference
- Local question answering

---

# Prototype Platform

The first BMASS prototype was deliberately built using entry-level consumer hardware.

The objective was not to maximise benchmark performance.

The objective was to demonstrate that a complete AI operating environment can boot directly from a USB drive and perform useful local inference on hardware that many people already own.

| Component | Specification |
|-----------|---------------|
| Computer | ASUS VivoBook E510KA |
| Processor | Intel® Celeron® N4500 |
| Memory | 4 GB DDR4-3200 |
| Graphics | Intel UHD Graphics (Jasper Lake) |
| Internal Storage | 115 GB eMMC |
| Boot Device | 8 GB SanDisk Cruzer Facet USB Flash Drive |
| Operating System | Alpine Linux |
| Inference Engine | llama.cpp |
| Language Model | Qwen3 0.6B GGUF (Q4_K_M) |

Despite these modest specifications, BMASS successfully boots into a fully local AI environment capable of offline inference without requiring cloud services after installation.

---

# Building the Prototype

The first prototype was developed from a blank USB drive rather than from a pre-built image.

The process consisted of:

1. Installing Alpine Linux onto an 8 GB USB flash drive.
2. Creating a dedicated BMASS runtime environment.
3. Compiling **llama.cpp** directly on the target system.
4. Downloading and installing a locally hosted Qwen3 GGUF model.
5. Creating a lightweight BMASS launcher.
6. Configuring the system to boot directly into the local language model.
7. Running entirely from removable media with no dependency on cloud inference after installation.

The result is a portable AI environment that can be carried on a USB drive and used on compatible hardware while remaining completely under the user's control.

---

# Current Features

- Bootable USB AI environment
- Alpine Linux base
- Offline local inference
- llama.cpp integration
- Local Qwen3 language model
- Lightweight launcher
- Portable installation
- Open-source software
- Reproducible build

---

# Repository Structure

```
launcher/          BMASS launcher
scripts/           Installation scripts
docs/              Documentation
examples/          Example configurations
config/            Configuration files
```

---

# System Architecture

```
            User
              │
              ▼
      BMASS Launcher
              │
              ▼
      llama.cpp Engine
              │
              ▼
     Local GGUF Model
              │
              ▼
      Local AI Inference
```

Future versions are planned to include:

- Model Context Protocol (MCP)
- Local system tools
- Document retrieval
- Persistent memory
- Multiple model management
- Model federation
- On-device fine-tuning

---

# Design Principles

BMASS is guided by several design objectives.

- Offline first
- User ownership
- Commodity hardware
- Lightweight Linux base
- Open source
- Fully reproducible
- Privacy by default

The project is not intended to replace Linux distributions.

Instead, it explores a different computing model in which the operating system exists primarily to support a local AI model.

---

# Roadmap

## Seed v0.1

- Bootable Model As System
- Alpine Linux
- llama.cpp
- Local Qwen model
- Offline inference

## v0.2

- Automatic login
- Improved launcher
- Installation scripts
- Configuration management

## v0.3

- Model Context Protocol (MCP)
- Local tools
- File management

## v0.4

- Multiple models
- Web interface
- Model switching

## v1.0

Portable AI operating environment.

---

# Contributing

Contributions, ideas, bug reports and pull requests are welcome.

BMASS is being developed openly, and the project will evolve incrementally as new ideas are explored and tested.

---

# Acknowledgements

BMASS builds upon outstanding open-source projects, including:

- Alpine Linux
- llama.cpp
- GGUF
- Qwen

Their work made this prototype possible.

---

# License

See the LICENSE file.

---

## About the Name

**BMASS** stands for **Bootable Model As System**.

It describes the central idea behind the project:

> **The model is the system.**

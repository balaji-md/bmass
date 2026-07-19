# Prototype Platform

The first BMASS prototype was deliberately built using entry-level consumer hardware rather than specialised AI hardware.

The goal was simple:

> **Demonstrate that a complete AI environment can boot directly from a USB drive and perform useful local inference on hardware that many people already own.**

## Hardware

| Component | Specification |
|-----------|---------------|
| Computer | ASUS VivoBook E510KA |
| Processor | Intel® Celeron® N4500 |
| Memory | 4 GB DDR4-3200 |
| Graphics | Intel UHD Graphics (Jasper Lake) |
| Internal Storage | 115 GB eMMC |
| BMASS Boot Media | 8 GB SanDisk Cruzer Facet USB Flash Drive |
| Operating System | Alpine Linux |
| Inference Engine | llama.cpp |
| Language Model | Qwen3 0.6B GGUF (Q4_K_M) |

Despite these modest specifications, BMASS successfully boots into a fully local AI environment capable of offline inference without requiring cloud services after installation.

---

# Building the Prototype

The prototype was developed incrementally rather than from a pre-built image.

The process consisted of:

1. Installing Alpine Linux onto an 8 GB USB flash drive.
2. Creating a dedicated BMASS runtime environment.
3. Compiling **llama.cpp** directly on the target system.
4. Downloading and installing a locally hosted Qwen3 GGUF model.
5. Creating a lightweight BMASS launcher.
6. Configuring the system to boot directly into the local language model.
7. Running entirely from removable media with no dependency on cloud inference.

The result is a portable AI environment that can be carried on a USB drive and used on compatible hardware while remaining completely under the user's control.

---

# Design Principles

BMASS was guided by several design objectives from the outset.

- Boot directly into AI
- Offline-first operation
- Commodity hardware
- Open-source software
- Lightweight Linux base
- Fully reproducible installation
- User ownership of both hardware and models

Rather than attempting to build another Linux distribution, BMASS explores a different question:

> **Can a language model become the primary interface to a computer?**

The operating system becomes a lightweight foundation whose primary purpose is to support the local model.

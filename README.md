# BMASS

## Bootable Model As System

> **The model is the system.**

# BMASS

## Bootable Model As System

> **Boot directly into an AI operating shell.**

BMASS is an open-source experiment that treats a local language model as the primary interface to a computer rather than another application running inside one.

Instead of booting a desktop and then opening an AI program, BMASS starts directly into a lightweight Linux environment where the AI becomes the operating interface.

The project explores a simple question:

**What if the model was the system?**

23 July 2026

# 🚀 Major Architecture Update (Experimental)

BMASS has undergone its largest architectural change since the project began.

The previous prototype relied on Python orchestration around the language model. That layer has now largely been removed. BMASS is moving towards becoming a native Unix resident compiled directly from C++ using the llama.cpp libraries.

Rather than acting as a conventional chatbot, BMASS now follows a perception–action loop:
User Request
↓
Model
↓
Shell Action
↓
Linux
↓
Observation
↓
Model
↓
Final Answer



The BMASS runtime has been recompiled with a shell execution layer. When the model determines that operating system information is required, it emits a `<shell>...</shell>` action. BMASS executes the command, captures the real output from Linux, feeds that observation back into the model, and allows the model to continue reasoning using actual system state rather than assumptions.

This removes a substantial amount of orchestration code while moving the intelligence closer to the operating system itself. The architecture is intentionally simple and is designed to evolve incrementally.

### Included in this update

- Native `bmass` executable
- `bmass.cpp` source
- Updated `system-prompt.txt`
- Shell execution runtime
- Screenshot demonstrating the perception–action loop

### Important

This remains an **experimental research project**.

The implementation is evolving rapidly and has only been tested on the reference BMASS environment.

Please check file paths before building or running, as your installation layout may differ.

Bug reports, pull requests and architectural suggestions are very welcome.

---

Thank you to everyone who has encouraged, tested, criticised and contributed ideas to BMASS. Your feedback has directly influenced the evolution of this project.



21 July 2026:
### Security

BMASS automatically executes only safe inspection commands.

Commands that modify the system require explicit operator approval before execution.

Privilege escalation commands are blocked.
---
### External Review

## BMASS was recently featured by Korben:

https://korben.info/bmass-boot-usb-modele-ia-local.html

Many thanks to Korben for taking the time to examine the project and provide an independent technical review.

Note: The embedded demonstration video in the article is the original proof-of-concept (BMASS Seed v0.5) that first demonstrated the architecture. The project has continued to evolve since that recording.

Following the review, BMASS has been updated to:

Fixed the system prompt path inconsistency.
Added explicit operator approval for modifying shell commands.
Restricted automatic execution to safe inspection commands.
Improved runtime safety and command handling.

Constructive external technical feedback continues to help improve the project



20th July 2026:

# Current Status (Seed v0.5)

BMASS has now completed its first operating-intelligence loop.

The current prototype boots from an **8 GB USB drive**, automatically launches a local language model, accepts natural language, executes Linux commands under a restricted user account, observes the operating system, and returns evidence-based responses.

No graphical desktop is required.

No internet connection is required after installation.

The entire system currently runs on an entry-level laptop with **4 GB RAM**.

---

# Architecture

```
Operator
      │
      ▼
Natural language
      │
      ▼
BMASS runtime
      │
      ▼
llama-server
      │
      ▼
Local language model
      │
      ▼
Command bridge
      │
      ▼
Linux operating system
      │
      ▼
Real command output
      │
      ▼
Evidence-based response
```

Unlike a conventional chatbot, BMASS does not simply describe the operating system.

It can inspect the machine, execute commands through a restricted Linux account, observe the results and continue the conversation using actual evidence returned from the computer.

---

# Demonstrated Features

Current BMASS prototypes demonstrate:

- Bootable USB AI environment
- Alpine Linux operating system
- Headless operation without a graphical interface
- Automatic launch of a local language model
- Offline inference after installation
- Local `llama-server` runtime
- Persistent BMASS operating interface
- Natural language interaction
- Safe command execution through a dedicated non-root Linux account
- Evidence-based responses using real operating-system output
- Portable operation from removable media

---

# What's New in Seed v0.5

This release introduces the first complete operating-intelligence loop.

Major architectural changes include:

- migration from a foreground inference process to a background `llama-server`
- persistent BMASS runtime
- automatic system-prompt injection
- separation of conversation and command execution
- restricted command execution through the dedicated `bmass` account
- startup diagnostics and health monitoring
- improved conversation continuity
- foundation for future local tools and agents

BMASS has now crossed from simply running a local language model to creating an AI-mediated operating shell.

---

# Project Goals

BMASS is not intended to replace existing operating systems.

It explores a different relationship between humans, operating systems and local AI.

The long-term objectives include:

- private AI by default
- offline-first computing
- portable AI environments
- user ownership of models and data
- open-source development
- inexpensive hardware
- reproducible bootable AI systems
- future local tools, memory and autonomous workflows

The aim is not to build the largest AI.

The aim is to make AI systems understandable, portable and personally owned.

---

# Current Prototype Hardware

| Component | Specification |
|-----------|---------------|
| Computer | ASUS VivoBook E510KA |
| Processor | Intel Celeron N4500 |
| Memory | 4 GB DDR4 |
| Graphics | Intel UHD Graphics |
| Boot Device | 8 GB USB flash drive |
| Operating System | Alpine Linux |
| Runtime | llama.cpp / llama-server |
| Model | Qwen3 0.6B GGUF (Q4_K_M) |

The prototype deliberately targets inexpensive consumer hardware to demonstrate that useful local AI does not require specialised workstations or cloud infrastructure.

---

# Repository Structure

```
launcher/
    bmass

config/
    system-prompt.txt

docs/

examples/

scripts/
```

Large models, compiled binaries and operating-system images are intentionally excluded from the repository.

The repository documents how BMASS is assembled rather than distributing copyrighted models.

---

# Current Development Status

Seed v0.5 is an experimental research prototype.

It demonstrates:

✓ Bootable AI environment

✓ Automatic model startup

✓ Headless AI shell

✓ Offline operation

✓ Local command execution

✓ Evidence-based responses

✓ Portable USB deployment

Current limitations include:

- prototype security model
- manual installation
- hard-coded configuration
- no persistent memory
- no package installer
- no automatic updates

Development continues in the open.

19th July 2026:

**BMASS** is an open-source experiment in making a local AI model the primary interface to a computer.

Instead of starting a conventional desktop and then opening an AI application, BMASS boots from a USB drive into a lightweight Linux environment. After login, the BMASS launcher automatically starts a local language model.

The model runs on the computer itself. Once the required software and model have been installed, internet access and cloud inference are not required.

🎥 **[Watch BMASS boot and run on an ordinary 4 GB laptop](https://youtube.com/shorts/HRQl7P-wd1w)**

---

## Why BMASS?

Artificial intelligence is often presented as something that requires expensive hardware, large data centres and permanent internet access.

BMASS demonstrates a smaller and more accessible possibility.

The first prototype runs from an **8 GB USB flash drive** on an entry-level laptop with only **4 GB of memory**. It uses free and open-source software and a small local language model.

The purpose is not to compete with the largest cloud models. It is to show that ordinary people can begin experimenting with private, portable and locally controlled AI using modest hardware.

---

## Demonstration

The short video below shows the prototype:

**[Watch the BMASS demonstration on YouTube](https://youtube.com/shorts/HRQl7P-wd1w)**

It demonstrates:

- Starting the computer from the BMASS USB drive
- Booting the Alpine Linux environment
- Launching BMASS
- Loading a local language model
- Running AI inference on the laptop itself

---

## Prototype Hardware

The first BMASS prototype was deliberately developed on entry-level consumer hardware.

| Component | Specification |
|---|---|
| Computer | ASUS VivoBook E510KA |
| Processor | Intel Celeron N4500 at 1.10 GHz |
| Memory | 4 GB DDR4-3200 |
| Graphics | Intel UHD Graphics, Jasper Lake |
| Internal storage | 115 GB eMMC |
| BMASS boot device | 8 GB SanDisk Cruzer Facet USB flash drive |
| BMASS operating system | Alpine Linux |
| Inference engine | llama.cpp |
| Language model | Qwen3 0.6B GGUF, Q4_K_M |

The prototype does not require a dedicated graphics card. Inference currently runs on the laptop’s CPU.

The objective was not maximum speed or benchmark performance. It was to test whether a complete local AI environment could boot from removable media and operate on hardware that many people already own.

---

## How the Prototype Was Built

BMASS was assembled from a blank USB drive rather than downloaded as a completed disk image.

The process was:

1. Partition an 8 GB USB flash drive.
2. Install Alpine Linux onto the USB.
3. Configure the USB as an independently bootable system.
4. Install the required development tools.
5. Build `llama.cpp` on Alpine Linux.
6. Download a quantised Qwen3 0.6B GGUF model.
7. Create a dedicated BMASS directory structure under `/opt/bmass`.
8. Install the `llama.cpp` runtime and model inside that environment.
9. Create the BMASS launcher.
10. Configure the launcher to start automatically after login on the main terminal.
11. Disable visible reasoning output for a cleaner interaction.

The current prototype therefore consists of a minimal Linux foundation, a local inference engine, a local model and a lightweight launcher.

---

## Current Architecture

```text
Computer firmware
        │
        ▼
BMASS USB bootloader
        │
        ▼
Alpine Linux
        │
        ▼
User login
        │
        ▼
BMASS launcher
        │
        ▼
llama.cpp
        │
        ▼
Local Qwen3 model
        │
        ▼
Offline AI interaction
```

---

## Current Prototype

The Seed prototype currently demonstrates:

- An independently bootable AI environment
- Operation entirely from an 8 GB USB drive
- Alpine Linux as a lightweight base
- Local CPU inference using `llama.cpp`
- A quantised Qwen3 0.6B model
- Automatic model startup after login
- Offline operation after installation
- A simple BMASS command-line interface

BMASS is currently a proof of concept. It is not yet a completed operating-system distribution or a one-command installer.

---

## Repository Contents

```text
launcher/
└── bmass       BMASS launcher
```

The repository will gradually be expanded with installation instructions, configuration files, build scripts and system documentation.

Large model files, compiled binaries and complete operating-system images are not stored directly in this repository.

---

## Design Principles

BMASS is guided by several principles:

- **Offline first** — local inference should not depend on a remote service.
- **User controlled** — the user owns the machine, environment and model.
- **Lightweight** — useful AI should be explored on modest hardware.
- **Open source** — the system should be inspectable and adaptable.
- **Portable** — the environment should be capable of running from removable media.
- **Private by default** — prompts and local files should not need to leave the computer.
- **Incremental** — the project should develop from a small working system rather than begin as a large theoretical design.

---

## What BMASS Is Not

BMASS is not currently a replacement for Alpine Linux.

It is not a new foundation model.

It is not intended to suggest that a 0.6B model can match the capabilities of large cloud-based systems.

BMASS is an exploration of a different relationship between the operating system and the model:

> Instead of AI being one application among many, the system is organised around the local model.

---

## Roadmap

### Seed v0.1

- [x] Bootable USB environment
- [x] Alpine Linux installation
- [x] `llama.cpp` runtime
- [x] Local Qwen3 model
- [x] BMASS launcher
- [x] Offline local inference
- [x] Public GitHub repository
- [x] Video demonstration

### v0.2

- [ ] Automatic login
- [ ] Improved startup experience
- [ ] Configurable model path
- [ ] Installation documentation
- [ ] Build and setup scripts
- [ ] Hardware compatibility testing

### v0.3

- [ ] Safe local tools
- [ ] File access with explicit permissions
- [ ] Model Context Protocol integration
- [ ] Local document retrieval
- [ ] Persistent configuration

### Later Development

- [ ] Multiple model support
- [ ] Model selection and switching
- [ ] Local web interface
- [ ] Persistent memory
- [ ] System recovery and rollback
- [ ] Reproducible BMASS disk images
- [ ] On-device adaptation and fine-tuning
- [ ] Communication between locally owned models

---

## Can Anyone Build It?

The current prototype still requires familiarity with Linux commands, disk partitioning and compiling software.

However, it was deliberately created with inexpensive hardware and freely available software. One of the project’s main goals is to turn the manual prototype process into clear documentation and repeatable installation tools.

The long-term aim is that a person should be able to prepare a USB drive, boot a compatible computer and run a private local AI without requiring specialised hardware or a cloud subscription.

---

## Contributing

Ideas, testing, bug reports and contributions are welcome.

BMASS is being developed openly from its earliest working prototype. Contributions that improve accessibility, documentation, hardware compatibility, safety or reproducibility are particularly valuable.

Please use GitHub Issues to report problems or suggest features.

---

## Acknowledgements

BMASS is made possible by existing open-source work, particularly:

- [Alpine Linux](https://alpinelinux.org/)
- [llama.cpp](https://github.com/ggml-org/llama.cpp)
- [Qwen](https://github.com/QwenLM/Qwen3)
- [GGUF](https://github.com/ggml-org/ggml)

BMASS does not redistribute the Qwen model or `llama.cpp` binaries. Users remain responsible for reviewing and complying with the licences of all external components.

---

## License

See the [LICENSE](LICENSE) file.

---

## About the Name

**BMASS** stands for **Bootable Model As System**.

It expresses the central idea of the project:

> **The model is the system.**

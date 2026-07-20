# BMASS Installation

These instructions install the BMASS launcher and system prompt on an existing Linux system.

BMASS currently expects:

- a Linux system
- Python 3
- `llama-server`
- a compatible GGUF language model
- a non-root user named `bmass`

The current prototype was developed on Alpine Linux, but the launcher may also work on other Linux distributions after paths are adjusted.

---

## 1. Clone the repository

```bash
git clone https://github.com/balaji-md/bmass.git
cd bmass
```

---

## 2. Create the BMASS user

BMASS executes operating-system commands through a restricted non-root account.

On Alpine Linux:

```bash
adduser bmass
```

Set a password when prompted.

Do not add the `bmass` user to privileged groups such as `wheel`.

---

## 3. Create the BMASS directories

```bash
mkdir -p /opt/bmass/bin
mkdir -p /opt/bmass/config
mkdir -p /opt/bmass/models
mkdir -p /opt/bmass/logs
```

---

## 4. Install the launcher

Copy the BMASS launcher:

```bash
cp launcher/bmass /usr/local/bin/bmass
```

Make it executable:

```bash
chmod 755 /usr/local/bin/bmass
```

---

## 5. Install the system prompt

```bash
cp config/system-prompt.txt /opt/bmass/config/system-prompt.txt
```

Restrict modification to root:

```bash
chown root:root /opt/bmass/config/system-prompt.txt
chmod 644 /opt/bmass/config/system-prompt.txt
```

---

## 6. Install llama-server

BMASS requires a working `llama-server` binary from `llama.cpp`.

Copy the binary into the BMASS directory:

```bash
cp /path/to/llama-server /opt/bmass/bin/llama-server
chmod 755 /opt/bmass/bin/llama-server
```

If `llama-server` depends on shared libraries, copy the required `.so` files into a directory under `/opt/bmass`, for example:

```bash
mkdir -p /opt/bmass/lib
cp /path/to/llama.cpp/libraries/*.so /opt/bmass/lib/
```

The BMASS launcher attempts to discover shared libraries stored under `/opt/bmass`.

---

## 7. Install a GGUF model

Copy a compatible GGUF model into:

```bash
/opt/bmass/models/
```

For example:

```bash
cp Qwen3-0.6B-Q4_K_M.gguf /opt/bmass/models/
```

The original prototype used a quantised Qwen3 0.6B GGUF model.

Large model files are not included in this repository.

Users are responsible for reviewing and complying with the model licence.

---

## 8. Check the launcher paths

Open the launcher:

```bash
nano /usr/local/bin/bmass
```

Confirm that the paths for the following match the local installation:

```text
llama-server
GGUF model
system-prompt.txt
log files
```

The current prototype may contain hard-coded paths that need to be changed for a different installation.

---

## 9. Test BMASS manually

Run:

```bash
/usr/local/bin/bmass
```

A successful startup should:

1. start `llama-server`
2. wait for the local server health check
3. display the BMASS prompt
4. accept normal conversation
5. execute permitted commands as the non-root `bmass` user

Example:

```text
BMASS> hello
```

Then test the restricted command environment:

```text
BMASS> whoami
```

The command should run as:

```text
bmass
```

It should not run as root.

---

## 10. Optional automatic startup

BMASS can be started automatically after login by adding the following to the intended user's shell profile:

```bash
if [ "$(tty)" = "/dev/tty1" ]; then
    exec /usr/local/bin/bmass
fi
```

Depending on the Linux distribution, this may be placed in:

```text
~/.profile
```

or another login startup file.

Test manual startup before enabling automatic startup.

---

## Security warning

BMASS is currently an experimental prototype.

Although commands are executed through a non-root user, this is not yet a hardened security sandbox.

Do not run BMASS on a system containing sensitive data or expose the local server to an untrusted network without additional isolation and review.

Recommended precautions include:

- run commands only as the restricted `bmass` user
- do not grant `sudo`, `doas`, `su`, or `wheel` access
- keep `llama-server` bound to localhost
- inspect the launcher before use
- use a disposable test machine or virtual machine
- back up important data

---

## Updating BMASS

From inside the cloned repository:

```bash
git pull
```

Then reinstall the updated files:

```bash
cp launcher/bmass /usr/local/bin/bmass
chmod 755 /usr/local/bin/bmass

cp config/system-prompt.txt /opt/bmass/config/system-prompt.txt
chown root:root /opt/bmass/config/system-prompt.txt
chmod 644 /opt/bmass/config/system-prompt.txt
```

Restart BMASS after updating.

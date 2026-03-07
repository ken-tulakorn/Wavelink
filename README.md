# Important:

The original Wavelink library is no longer maintained. **This repository is a patched community fork** designed to keep Wavelink alive by adding support for Discord's DAVE (E2EE) voice update and Lavalink 4.2.2+.

<div align="center">

![Logo](https://raw.githubusercontent.com/PythonistaGuild/Wavelink/master/logo.png)

![Python Version](https://img.shields.io/pypi/pyversions/Wavelink)
[![Github License](https://img.shields.io/github/license/PythonistaGuild/Wavelink)](LICENSE)
[![Lavalink Version](https://img.shields.io/badge/Lavalink-v4.2.2%2B-blue?color=%23FB7713)](https://lavalink.dev)
![Lavalink Plugins](https://img.shields.io/badge/Lavalink_Plugins-Native_Support-blue?color=%2373D673)

</div>

Wavelink is a robust and powerful Lavalink wrapper for [Discord.py](https://github.com/Rapptz/discord.py). Wavelink features a fully asynchronous API that's intuitive and easy to use.

---

## 🌟 What is this fork?
Since Discord's recent enforcement of the **DAVE (End-to-End Encryption)** voice system, Lavalink **v4.2.1+** strictly requires the `channelId` to be passed in the VoiceState payload. The original Wavelink library does not send this, resulting in the following error and a lack of audio output:

`HttpMessageNotReadableException: Field 'channelId' is required... but it was missing`

**This fork fixes that issue** by automatically injecting the required `channelId` into the `_dispatch_voice_update` method, allowing your bot to connect and play music flawlessly on Lavalink 4.2.2 and newer!

### Features

- **Discord DAVE (E2EE) Voice Support (Patched)**
- Full asynchronous design.
- Lavalink v4.2.2+ Supported with REST API.
- discord.py v2.0.0+ Support (v2.7.1+ Recommended).
- Advanced AutoPlay and track recommendations for continuous play.
- Object orientated design with stateful objects and payloads.
- Fully annotated and complies with Pyright strict typing.

## Installation

**WaveLink 3 requires Python 3.10+**

To use this patched version, first, uninstall the original Wavelink library from your environment, then install directly from this repository:

```sh
# 1. Uninstall the broken version
pip uninstall wavelink -y

# 2. Install this patched fork
pip install git+https://github.com/ken-tulakorn/Wavelink.git

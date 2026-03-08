# solivram — Official Releases

<p align="center">
  <img src="https://github.com/Solivram/solivram/raw/main/solivram.png" alt="solivram logo" width="140"/>
</p>

<p align="center">
  <a href="https://github.com/Solivram/solivram-releases/blob/main/README.md">
    <img src="https://img.shields.io/badge/🇫🇷%20Français-0055A4?style=for-the-badge" alt="Français"/>
  </a>

  <a href="https://github.com/Solivram/solivram-releases/blob/main/README_EN.md">
    <img src="https://img.shields.io/badge/🇬🇧%20English-012169?style=for-the-badge" alt="English"/>
  </a>
</p>

> High-availability distributed infrastructure, post-quantum secured, observable and extensible, built in pure Rust for critical environments.

<p align="center">
  <a href="https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/solivram_0.1.0_amd64.deb">
    <img src="https://img.shields.io/badge/⬇️%20Download%20solivram%20v0.1.0%20(.deb)-2ea44f?style=for-the-badge" alt="Download"/>
  </a>
</p>

---

## Information

| Field      | Value                               |
|------------|-------------------------------------|
| Author     | Jenka Nauta                         |
| Version    | 0.1.0                               |
| Date       | 2026-03-08                          |
| Licence    | MIT                                 |
| Type       | Server / Daemon                     |
| Origin     | France                              |
| Github     | https://github.com/Solivram         |
| Phase      | 146 — 1088 tests passed             |

---

## Categories

`Security` · `Distributed Infrastructure` · `Post-Quantum Cryptography` · `Rust`

---

## Core capabilities

| Module | Description |
|--------|-------------|
| **Raft HA Cluster** | Election, replication, snapshot, dynamic membership |
| **Internal X.509 PKI** | Root CA, intermediate, leaf certs, CRL |
| **Sovereign DNS + DNSSEC** | Dual P-256 + ML-DSA-65 |
| **PQC Hybridization** | ML-KEM-768 (encapsulation) + ML-DSA-65 (signature) |
| **REST API** | Axum — Bearer auth, RBAC 5 roles, rate-limiter, CORS |
| **Encrypted Storage** | redb + AES-256-GCM + key rotation |
| **HA Reverse Proxy** | Circuit-breaker, dynamic backends |
| **Native GUI** | egui interface |
| **Secure Sessions** | TTL 1h + 2FA TOTP RFC 6238 |

---

## Installation

### Debian / Ubuntu

```bash
# Via curl (recommended)
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/solivram_0.1.0_amd64.deb && sudo dpkg -i solivram_0.1.0_amd64.deb

# Or download manually
sudo dpkg -i solivram_0.1.0_amd64.deb
solivram --help
```

**Dependencies** : `libwayland-client0` · `libudev1` · `libasound2` · `libgcc-s1` · `libc6` · `libffi8` · `libcap2`

---

## Signature verification

```bash
solivram identity:verify
# ✅ P-256 valid | ✅ ML-DSA valid
```

**P-256 public key:**
```
04fa81886487fa97a92bf77756252ffbb17cfdec1ca55131e7bf94920a14f00faf6af84fb9680f1d3c367cba6c09fa17dc1e2edd3005173ed599fcc091973a3091
```

---

## Documentation

| Document | Français | English |
|----------|----------|---------|
| **Quickstart** | [Solivram_Quickstart.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Quickstart.pdf) | [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Quickstart_EN.pdf) |

---

## Sector pitches

| Sector | Français | English |
|--------|----------|---------|
| Defense | [Pitch_Defense_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Defense_FR.pdf) | [Pitch_Defense_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Defense_EN.pdf) |
| Healthcare | [Pitch_Sante_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Sante_FR.pdf) | [Pitch_Healthcare_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Healthcare_EN.pdf) |
| Finance | [Pitch_Finance_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Finance_FR.pdf) | [Pitch_Finance_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Finance_EN.pdf) |
| AI Agents | [Pitch_Agents_IA_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Agents_IA_FR.pdf) | [Pitch_Agents_IA_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.1.0/Solivram_Pitch_Agents_IA_EN.pdf) |

---

## Links

- Presentation: https://github.com/Solivram/solivram
- All releases: https://github.com/Solivram/solivram-releases/releases

---

*solivram — Jenka Nauta — France — 2026*

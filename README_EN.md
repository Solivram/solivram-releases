# solivram — Official Releases

<p align="center">
  <img src="https://github.com/Solivram/solivram/raw/main/solivram.png" alt="solivram logo" width="140"/>
</p>

<p align="center">
  <a href="https://github.com/Solivram/solivram-releases/blob/main/README.md"><strong>🇫🇷 Français</strong></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/Solivram/solivram-releases/blob/main/README_EN.md"><strong>🇬🇧 English</strong></a>
</p>

> High-availability distributed infrastructure, post-quantum secured, observable and extensible, built in pure Rust for critical environments.

<p align="center">
  <a href="https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb">
    <img src="https://img.shields.io/badge/⬇️%20Download%20solivram%20v0.2.0%20(.deb)-2ea44f?style=for-the-badge" alt="Download"/>
  </a>
</p>

---

## Information

| Field      | Value                               |
|------------|-------------------------------------|
| Author     | Jenka Nauta                         |
| Version    | 0.2.0                               |
| Date       | 2026-03-23                          |
| Licence    | MIT                                 |
| Type       | Server / Daemon                     |
| Origin     | France                              |
| Github     | https://github.com/Solivram         |
| Phase      | 212 — 1370 tests passed             |

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
| **E2E Encryption** | ML-KEM-768 + AES-256-GCM, end-to-end between clients |
| **Inter-node Trust** | Trust signals, admin accept/revoke API |
| **Native GUI** | egui interface |
| **Secure Sessions** | TTL 1h + 2FA TOTP RFC 6238 |

---

## System requirements

- **OS** : Debian 11+ / Ubuntu 20.04+ (amd64 x86-64)
- **Architecture** : x86-64 only

```bash
uname -m  # should display x86_64
```

## Installation

```bash
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo dpkg -i solivram_0.2.0_amd64.deb
solivram --help
```

**Dependencies** : `libwayland-client0` · `libudev1` · `libasound2` · `libgcc-s1` · `libc6` · `libffi8` · `libcap2`

```bash
# Allow ports < 1024 without root
sudo setcap cap_net_bind_service=+ep /usr/bin/solivram
```

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

## First start

```bash
solivram --config /etc/solivram/default.toml headless
solivram --config /etc/solivram/default.toml api
```

## Uninstall

```bash
sudo dpkg -r solivram
```

---

## Documentation

| Document | Français | English |
|----------|----------|---------|
| **Warning & map** | [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) |
| **Quickstart** | [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_EN.pdf) |
| **Overview** | [Solivram_Overview_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Overview_FR.pdf) | [Solivram_Overview_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Overview_EN.pdf) |
| **Admin guide** | [Solivram_Guide_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Guide_Admin_FR.pdf) | [Solivram_Guide_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Guide_Admin_EN.pdf) |
| **Production config** | [Solivram_Config_Prod_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_FR.pdf) | [Solivram_Config_Prod_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_EN.pdf) |
| **Full configuration** | [Solivram_Config_Prod_full_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_full_FR.pdf) | [Solivram_Config_Prod_full_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_full_EN.pdf) |
| **Exception hot-reload security_level** | [FR](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Exception_Hot_Reload_Security_Level_FR.pdf) | [EN](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Exception_Hot_Reload_Security_Level_EN.pdf) |
| **Roadmap v0.2.0** | [Solivram_Roadmap_v0.2.0_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Roadmap_v0.2.0_FR.pdf) | [Solivram_Roadmap_v0.2.0_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Roadmap_v0.2.0_EN.pdf) |
| **Architecture** | [Solivram_Architecture.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Architecture.pdf) | [Solivram_Architecture_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Architecture_EN.pdf) |
| **Developer guide** | [Solivram_Manuel_Dev.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Manuel_Dev.pdf) | [Solivram_Manuel_Dev_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Manuel_Dev_EN.pdf) |

---

## Release files

> GitHub truncates the asset list — complete list below.

| File | Description |
|------|-------------|
| [solivram_0.2.0_amd64.deb](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb) | Debian package — main installation |
| [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | Warning, map, prerequisites (FR) |
| [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) | Installation warning & map (EN) |
| [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | Quick start guide (FR) |
| [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_EN.pdf) | Quick start guide (EN) |
| [Solivram_Overview_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Overview_FR.pdf) | Project overview (FR) |
| [Solivram_Overview_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Overview_EN.pdf) | Project overview (EN) |
| [Solivram_Guide_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Guide_Admin_FR.pdf) | Complete admin guide (FR) |
| [Solivram_Guide_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Guide_Admin_EN.pdf) | Complete admin guide (EN) |
| [Solivram_Config_Prod_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_FR.pdf) | Production configuration — example (FR) |
| [Solivram_Config_Prod_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_EN.pdf) | Production configuration — example (EN) |
| [Solivram_Config_Prod_full_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_full_FR.pdf) | Full configuration — TOML reference (FR) |
| [Solivram_Config_Prod_full_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Config_Prod_full_EN.pdf) | Full configuration — TOML reference (EN) |
| [Solivram_Exception_Hot_Reload_Security_Level_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Exception_Hot_Reload_Security_Level_FR.pdf) | Exception hot-reload security_level (FR) |
| [Solivram_Exception_Hot_Reload_Security_Level_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Exception_Hot_Reload_Security_Level_EN.pdf) | Exception hot-reload security_level (EN) |
| [Solivram_Pitch_Defense_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_FR.pdf) | Defense pitch (FR) |
| [Solivram_Pitch_Defense_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_EN.pdf) | Defense pitch (EN) |
| [Solivram_Pitch_Sante_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Sante_FR.pdf) | Healthcare pitch (FR) |
| [Solivram_Pitch_Healthcare_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Healthcare_EN.pdf) | Healthcare pitch (EN) |
| [Solivram_Pitch_Finance_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_FR.pdf) | Finance pitch (FR) |
| [Solivram_Pitch_Finance_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_EN.pdf) | Finance pitch (EN) |
| [Solivram_Pitch_Agents_IA_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_FR.pdf) | AI Agents pitch (FR) |
| [Solivram_Pitch_Agents_IA_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_EN.pdf) | AI Agents pitch (EN) |
| [Solivram_Pitch_Energie_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energie_FR.pdf) | Energy / Industry pitch (FR) |
| [Solivram_Pitch_Energy_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energy_EN.pdf) | Energy / Industry pitch (EN) |
| [Solivram_Pitch_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_FR.pdf) | Government pitch (FR) |
| [Solivram_Pitch_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_EN.pdf) | Government pitch (EN) |
| [Solivram_Roadmap_v0.2.0_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Roadmap_v0.2.0_FR.pdf) | Roadmap v0.2.0 (FR) |
| [Solivram_Roadmap_v0.2.0_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Roadmap_v0.2.0_EN.pdf) | Roadmap v0.2.0 (EN) |
| [Solivram_Architecture.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Architecture.pdf) | Project architecture (FR) |
| [Solivram_Architecture_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Architecture_EN.pdf) | Project architecture (EN) |
| [Solivram_Manuel_Dev.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Manuel_Dev.pdf) | Developer guide (FR) |
| [Solivram_Manuel_Dev_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Manuel_Dev_EN.pdf) | Developer guide (EN) |

---

## Changelog

### v0.2.0 — Phase 212 (2026-03-23) — Startup anomalies fix
- **PkiRedbGuard false positive** (A1): `pki_guard.init()` moved after ALL startup PKI writes (secrets ×3, gossip cert, TLS API cert) — eliminates false alarm at tick=0 (`0u64.is_multiple_of(600)==true`)
- **EventBus WARN no subscriber** (A2): `alerte_rx = bus.subscribe()` created in `start()` BEFORE `publish(AppStarted)` — receiver passed as parameter to `run_loop()`, no event loss at startup
- **Clean build**: `rm -rf target/` + `rm data/*.redb` before `cargo build --release` — binary `2026-03-23 10:14`
- 1370 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phase 211 (2026-03-22) — Complete memory audit
- **Memory audit** (Phases 209–211): 13 issues identified and resolved (2 CRITICAL, 4 HIGH, 4 MEDIUM, 3 COMPLIANT)
- **RateLimiter TTL purge** (Phase 209): `DashMap::retain()` + `RETENTION_MULT=10` constant — eliminates unbounded growth
- **JenkaKv watch capacity** (Phase 209): `WATCH_BROADCAST_CAPACITY=1024` + `Arc<AtomicU64>` drop counter — loss detection
- **LookupCache expiry filter** (Phase 209): expired tokens filtered at HashMap rebuild — no memory leak
- **EventBus capacity** (Phase 210): `EVENTBUS_DEFAULT_CAPACITY=256` + drop counter shared between clones
- **KV watch bulkhead** (Phase 210): `MAX_KV_WATCH_ENTRIES=1000` — bounds DashMap iteration
- **Audit VecDeque** (Phase 210): `MAX_AUDIT_ENTRIES=100` constant — replaces magic number
- **ColdTier bulkhead** (Phase 211): `Semaphore::try_acquire()` + `N_MAX_COLD_READS=4` — caps at 4×256 MiB concurrent reads
- **Ordering::Relaxed doc** (Phase 211): exhaustive justification in `metrics.rs` — no logic change
- 1370 tests · clean build · clippy 0 warnings

### v0.2.0 — Phase 208 (2026-03-22)
- **PKI CA Fingerprint TOFU** (Phase 207): `GET /api/pki/ca/fingerprint` (public) + `GET /api/pki/ca/cert` (Bearer) — chain/root/intermediate PEM · `/etc/solivram/pki_fingerprint.txt` written at startup
- **PkiRedbGuard** (Phase 208): `pki.redb` tampering detection every 60s · partial SHA-256 (8KB header+tail) + full hash if anomaly · `Zeroizing<[u8;32]>` + `mlock()` · detection window ≤ 60s · Prometheus metrics `pki_redb_tampered_total`
- `/api/security/status` +3 fields: `pki_redb_hash_ok`, `pki_redb_tampered`, `pki_ca_mismatch`
- **Package fix**: `/etc/solivram/` chmod `750` → `770` — solivram group can now create `pki_fingerprint.txt` at startup
- 1344 tests · clean build · clippy 0 warnings

### v0.2.0 — Phase 205 (2026-03-21)
- **Raft peer address fix** (Phase 192): peer port correctly derived from local port → Raft port
- **StorageManager + EncryptedBackend** (Phase 193): AES-256-GCM encrypted HA KV cache in front of JenkaKv
- **TopologyMode** (Phase 194): Local/WAN/Cloud network configuration, adaptive Raft timeouts
- **GET /api/cluster/nodes** (Phase 195): multi-cloud node discovery endpoint
- **TlsEnforcer** (Phase 196): TLS/PQC enforcement by topology (wan/cloud mandatory)
- **Security fixes** (Phase 197) + **performance** (Phase 198) + **pipeline** (Phases 199-200)
- **Machine Binding v2 + K_user v2** (Phases 201-202): user key derivation tied to machine anchor, `/api/admin/users/rekey` endpoint
- **ApiMode TLS warn** (Phase 204): warn emitted if tls_mode="required" without PKI resolver in standalone api mode
- **Clippy fixes** (Phase 205): W1-W5 let chains + u64 cast, B6-5 mdns+topology wan/cloud warn
- 1325 tests · clean build · clippy 0 warnings

### v0.2.0 — Phase 191 (2026-03-20)
- **PKI Key Usage fixed** (Phase 190): X.509 certificates now carry correct `digitalSignature` KeyUsage — resolves curl SSL error 60 "unsuitable certificate purpose"
- **Gossip TLS retry backoff** (Phase 191): automatic reconnection after hot-swap failure (backoff 10 s → 30 s → 60 s), admin alert after 3 consecutive failures
- 1259 tests · clean build · clippy 0 warnings

---

## FAQ

**Q: Does Rust need to be installed to use solivram?**
No. The `.deb` package contains a pre-compiled binary. Rust is only required to build from source.

**Q: Does solivram work on ARM / Raspberry Pi?**
Not yet. Only amd64 (x86-64) architecture is supported in v0.2.0.

**Q: Is the binary signed?**
Yes. Solivram embeds a P-256 + ML-DSA-65 identity verifiable via `solivram identity:verify`.

**Q: How to update solivram?**
```bash
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo dpkg -i solivram_0.2.0_amd64.deb
```

## Sector pitches

| Sector | Français | English |
|--------|----------|---------|
| Defense | [Pitch_Defense_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_FR.pdf) | [Pitch_Defense_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_EN.pdf) |
| Healthcare | [Pitch_Sante_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Sante_FR.pdf) | [Pitch_Healthcare_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Healthcare_EN.pdf) |
| Finance | [Pitch_Finance_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_FR.pdf) | [Pitch_Finance_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_EN.pdf) |
| AI Agents | [Pitch_Agents_IA_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_FR.pdf) | [Pitch_Agents_IA_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_EN.pdf) |
| Energy / Industry | [Pitch_Energie_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energie_FR.pdf) | [Pitch_Energy_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energy_EN.pdf) |
| Government | [Pitch_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_FR.pdf) | [Pitch_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_EN.pdf) |

---

## Links

- Presentation: https://github.com/Solivram/solivram
- All releases: https://github.com/Solivram/solivram-releases/releases

---

*solivram — Jenka Nauta — France — 2026*


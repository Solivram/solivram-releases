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
| Date       | 2026-04-06                          |
| Licence    | MIT                                 |
| Type       | Post-Quantum Infrastructure Engine  |
| Origin     | France                              |
| Github     | https://github.com/Solivram         |
| Phase      | 271 — 1722 tests passed             |

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
| **nftables Firewall** | Integrated nftables management — strict/permissive modes, ambient capabilities, declarative outbound whitelist |
| **Inter-cluster Federation** | KV/CRL sync across clusters, quarantine, federated trust |
| **Encrypted Backup** | AES-256-GCM snapshots, remote upload, automatic scheduler |
| **Cognitive Memory** | 18 `/api/memory/*` endpoints, SQLite WAL, TF-IDF, TOML rate limiters |

---

## System requirements

- **OS** : Debian 11+ / Ubuntu 20.04+ (amd64 x86-64)
- **Architecture** : x86-64 only

```bash
uname -m  # should display x86_64
```

## Installation

```bash
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo apt install ./solivram_0.2.0_amd64.deb
solivram --help
```

**Dependencies** : `libwayland-client0` · `libudev1` · `libasound2` · `libgcc-s1` · `libc6` · `libffi8` · `libcap2` · `libcap2-bin` · `nftables`

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
# Uninstall (keeps config and data)
sudo apt remove solivram

# Full uninstall (also removes config files)
sudo apt purge solivram

# Full data removal (databases, certificates, keys)
sudo rm -rf /var/lib/solivram/ /etc/solivram/
```

---

## Documentation

| Document | Français | English |
|----------|----------|---------|
| **Warning & map** | [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) |
| **Quickstart** | [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_EN.pdf) |

---

## Release files

> GitHub truncates the asset list — complete list below.

| File | Description |
|------|-------------|
| [solivram_0.2.0_amd64.deb](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb) | Debian package amd64 (x86-64) |
| [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | Mise en garde & cartographie officielle — Français |
| [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) | Installation Warning & Official Map — English |
| [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | Quick Start Guide — Français |
| [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_EN.pdf) | Quick Start Guide — English |
| [Solivram_Pitch_Defense_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_FR.pdf) | Pitch Défense — Français |
| [Solivram_Pitch_Defense_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_EN.pdf) | Pitch Defense — English |
| [Solivram_Pitch_Sante_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Sante_FR.pdf) | Pitch Santé — Français |
| [Solivram_Pitch_Healthcare_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Healthcare_EN.pdf) | Pitch Healthcare — English |
| [Solivram_Pitch_Finance_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_FR.pdf) | Pitch Finance — Français |
| [Solivram_Pitch_Finance_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_EN.pdf) | Pitch Finance — English |
| [Solivram_Pitch_Agents_IA_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_FR.pdf) | Pitch Agents IA — Français |
| [Solivram_Pitch_Agents_IA_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_EN.pdf) | Pitch AI Agents — English |
| [Solivram_Pitch_Energie_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energie_FR.pdf) | Pitch Énergie / Industrie — Français |
| [Solivram_Pitch_Energy_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energy_EN.pdf) | Pitch Energy / Industry — English |
| [Solivram_Pitch_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_FR.pdf) | Pitch Administrations — Français |
| [Solivram_Pitch_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_EN.pdf) | Pitch Government — English |

---

## Changelog

### v0.2.0 — Phases 256–271 (2026-04-06) — Cognitive memory + TF-IDF + Configurable rate limiters

- **Cognitive memory module**: SQLite WAL + 18 `/api/memory/*` endpoints — AES-256-GCM encrypted storage, Bearer RBAC, per-context quotas
- **TF-IDF search engine**: cosine similarity sparse, LIKE fallback, snippet preview, SearchRateLimiter
- **Configurable TOML rate limiters**: `[server]` global, `[memory]` contexts/search/prcsr — full backward compatibility
- **Enriched tokenization**: compound sub-terms (`ml-kem` → `ml-kem + kem`), numeric filters, semantic bigrams
- **CLI**: `memory:status`, `memory:contexts`, `memory:search`, `memory:reindex`, `memory:index:stats`
- **TUI/GUI**: MemoryPanel + MemoryGuiPanel — dirty flag, update() + render_text()
- 69 tests added — 1653 → 1722 · clippy 0 errors · fmt ✅

### v0.2.0 — Phase 255 (2026-04-04) — A-SEC-255: Endpoint protection + local mode security

- **`/api/node` + `/api/config`** → `api_protegees` — Bearer + RBAC required (moved from public)
- **`services[]`** removed from public JSON `manifest.rs` — reconnaissance map removed
- **`secure_display`**: new `[display]` field — masks operational data in TUI/GUI panels for multi-user environments
- **`require_local_auth`**: admin token required before terminal/GUI startup — constant-time comparison
- 11 tests added — 1642 → 1653 · clippy 0 errors · fmt ✅

### v0.2.0 — Phases 249-253 (2026-04-04) — Least-privilege outbound audit

- **A-SEC-01 (Phase 249)**: `cluster_allowed_cidrs_v4/v6 = []` — dual-mode cluster input: `[]` = dynamic (`@cluster_peers`), non-empty = static CIDR from config
- **A-SEC-02 (Phase 250)**: `construire_script_activation_filtre_cluster()` dual-mode consistent across full firewall lifecycle
- **A-OUT-01 (Phase 251)**: cluster output restricted to `tcp dport @cluster_listen_ports` (gossip/raft/api/federation) — least privilege
- **A-OUT-02 (Phase 252)**: `dns_servers`/`ntp_servers` — optional destination IP filter — anti-DNS-tunneling, anti-NTP-hijacking
- **A-OUT-03 (Phase 253)**: `AllowedDestinationPort {cidr, tcp_ports, udp_ports}` — per-port CIDR granularity + `warn!` if `allowed_destinations_v4/v6` non-empty
- 1642 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phase 247 (2026-03-30) — Declarative outbound whitelist + hot-reload

- **`[firewall.outbound_services]`**: declarative whitelist in `config.toml` — fail-secure defaults (`dhcp=true ntp=true`, rest `false/[]`)
- **Configurable**: `dhcp` · `ntp` · `https` · `http` · `extra_tcp_ports` · `extra_udp_ports` · `allowed_destinations_v4/v6`
- **Hot-reload**: `POST /api/config/reload` → rebuilds `chain output` + `chain input` without restart
- **Situation matrix**: prod-solo / prod-static-IP / dev-solo / staging / headless-embed documented in `config.toml`
- 1622 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phases 244–246 (2026-03-29/30) — Critical firewall fixes (field TP)

- **Phase 244**: `exthdr frag exists drop` (IPv6 fragment fix) — firewall active at startup, 12 imports cleaned
- **Phase 245 BUG-1**: `stop()` `nft flush table` → `nft delete table` — network not blocked after solivram restart
- **Phase 245 BUG-2**: federation output missing in strict mode → half-duplex → fixed (`@federation_peers_ipv4/v6 tcp 8433`)
- **Phase 246 BUG-3**: open mode blocked internet → input chain rebuild + `ct state established,related accept`
- **Phase 246 BUG-4**: DHCP blocked → WiFi no IP at startup (`ERR_INTERNET_DISCONNECTED`) → UDP 67 allowed
- **Phase 246 NTP**: NTP missing → clock drift → PKI invalid → mTLS failure → UDP 123 allowed
- 1616 tests Phase 246 · clippy 0 warnings · fmt ✅

### v0.2.0 — Phases 241–243 (2026-03-29) — P1 Pillar 1: Backup & Restore complete

- **BackupEngine** (Phase 241): encrypted snapshots AES-256-GCM per-file, SHA3-256 manifest, CLI `backup` / `backup --verify` / `restore`
- **RemoteUploader** (Phase 242): 3 backends (`path` NFS/CIFS · `s3` aws CLI · `sftp` rsync+ssh), anti-path-traversal, 300s subprocess timeout, CLI `backup --remote`
- **BackupScheduler** (Phase 243): tokio background task, `backup_interval_secs`, SharedState `backup:last_at/status`, CLI `backup --auto`
- Clean build: `rm -rf target/` + `cargo build --release` — binary `2026-03-29`
- 1607 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phases 230–240 (2026-03-29) — Inter-cluster Federation

- **FederationService** (Phase 230): 14 REST endpoints `/api/federation/*`, ML-DSA-65 + HMAC-SHA3-256 signed messages, federation.redb store
- **FederationTrustStore** (Phase 231): trust states (Pending/Trusted/Revoked/Blocked), TOFU-compatible trust decision engine
- **FederationEnforcer** (Phase 232): policy enforcement (open/strict/isolated modes), DecisionEnforcer RBAC
- **FederationTransport** (Phase 233): mTLS inter-cluster transport, token derivation `deriver_hmac_key_federation`
- **FederationDiscovery** (Phase 234): DNS + direct endpoint resolution, multi-address support
- **FederationSyncService** (Phase 235–240): KV/CRL synchronization, gossip propagation, cluster health monitoring
- 132 federation tests · NftablesManager `solivram_filter_federation` sets · API RBAC Admin

### v0.2.0 — Phases 226–229 (2026-03-28) — Security + performance audit
- **S1**: 5s timeout on Raft TCP pool lock — eliminates indefinite block on dead connection
- **P1+P2**: `fn hex_sha3()` HMAC hot path — 0 intermediate allocation per Raft message
- **S2/S3**: `.expect()` production → `match+panic!()` · UNIX_EPOCH clock → `unwrap_or_else + log`
- **S4**: sweep ~80 `.expect()`/`.unwrap()` in `#[cfg(test)]` (~20 files + nftables)
- **P3/P4**: `Vec::with_capacity` DNS · `DashMap<SocketAddr>` TCP pool (inline key, no alloc)
- **F1/F2/F3**: Phase 189 dead code removed · `input.rs` placeholder cleaned up
- Clean build: `rm -rf target/` + `cargo build --release` — binary `2026-03-28`
- 1475 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phase 225 (2026-03-27) — Fix firewall_mode:unavailable + sudo-rs / Linux 7.0 compatibility
- **Ambient capabilities**: `nft_cmd()` helper with `pre_exec` → `SYS_capget` + `SYS_capset` + `prctl(PR_CAP_AMBIENT_RAISE, CAP_NET_ADMIN)` — `nft` inherits `cap_net_admin` via ambient → `firewall_mode: active`
- **Root cause resolved**: `CapInh=0`, `CapAmb=0` in solivram process → spawned `nft` subprocess gets no capability → EPERM. Fix: targeted propagation in child only after `fork()`
- ✅ **sudo-rs compatible**: solivram is compatible with [sudo-rs](https://github.com/trifectatechfoundation/sudo-rs), the Rust rewrite of sudo, on Linux 7.0
- **Clean build**: `rm -rf target/` + `cargo build --release` — binary `2026-03-27`
- 1478 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phases 221–224 (2026-03-24) — Firewall integration across all execution modes
- **ApiMode** (Phase 221): publishes `PortBound{api,port}` + `NetworkModeChanged` at startup — standalone NftablesManager initialized in api-only mode
- **UnifiedMode** (Phase 222): HeadlessMode opens API port in firewall after `run_loop()` init (resolves `tokio::spawn` timing)
- **TerminalMode TUI** (Phase 223): `MonitoringPanel` displays `fw:strict` / `fw:open` / `fw:N/A` in real time
- **GuiMode egui** (Phase 224): "Firewall outbound" row in PQC Security panel — green/yellow/grey colors + FR/EN translations
- **Clean build**: `rm -rf target/` + `cargo build --release` — binary `2026-03-24`
- 1479 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phases 215–220 (2026-03-24) — NftablesManager kernel firewall + full wiring
- **NftablesManager** (Phases 215–220): 100% Rust kernel firewall module via `nft -f /dev/stdin` (`cap_net_admin`)
- **Kernel INBOUND firewall**: 5 chains + 9 nftables sets — `input` policy drop, SYN flood rate limit, cluster peers/API/Prometheus dual-stack IPv4+IPv6 allowlist
- **Kernel OUTBOUND firewall**: `chain output` policy drop in `network.mode=strict` — only allowed: loopback, established connections, cluster peers, DNS 53, mDNS 5353 if multicast active. Ports 443/80 blocked at kernel level.
- **30s bootstrap**: temporary rule without IP source filter → seeds join → strict IP filter activated (`completer_bootstrap()`)
- **100ms HP batching**: grouped operations (open/close port, add/remove peer) in a single nft call
- **60s health check**: `nft list set` → mirror comparison → automatic restoration if divergence detected
- **Prometheus observability**: `jenka.firewall.batch_flushes_total`, `jenka.firewall.integrity_checks_total`, `jenka.firewall.divergences_detected_total`
- **`/api/security/status`** +4 fields: `firewall_mode`, `firewall_outbound_mode`, `firewall_peers_v4_count`, `firewall_peers_v6_count`
- 1469 tests · clippy 0 warnings · fmt ✅

### v0.2.0 — Phase 213 (2026-03-23) — Startup audit + log fixes + config sync
- **Double NodeIdentity log**: `tracing::info!` moved from shared functions (`generer_avec_san_et_domaine`) to callers (`emettre_gossip_*` / `emettre_api_*`) — distinct "gossip" and "API TLS" labels in logs
- **Sync `config/default.toml`**: source synchronized with installed postinst template (+`env`, `log_level`, `host`, `port`, `token_ttl_secs`, `admin_token`, `max_body_bytes`)
- **Startup audit**: 10 field configurations analyzed — nftables IP/port filter only, two distinct TLS layers, `discovery_enabled` ≠ `mdns_enabled`
- 1370 tests · clippy 0 warnings · fmt ✅

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
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo apt install ./solivram_0.2.0_amd64.deb
```

---

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


# solivram — Releases officielles

<p align="center">
  <img src="https://github.com/Solivram/solivram/raw/main/solivram.png" alt="solivram logo" width="140"/>
</p>

🇫🇷 [Français](README.md) · 🇬🇧 [English](README_EN.md)

> Infrastructure distribuée haute disponibilité, sécurisée post-quantique, observable et extensible, conçue en Rust pur pour des environnements critiques.

<p align="center">
  <a href="https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb">
    <img src="https://img.shields.io/badge/⬇️%20Télécharger%20solivram%20v0.2.0%20(.deb)-2ea44f?style=for-the-badge" alt="Télécharger"/>
  </a>
</p>

---

Package Solivram compatible ARM64 bientôt disponible.

---

## Informations

| Champ      | Valeur                              |
|------------|-------------------------------------|
| Auteur     | Jenka Nauta                         |
| Version    | 0.2.0                               |
| Date       | 2026-04-06                          |
| Licence    | MIT                                 |
| Type       | Post-Quantum Infrastructure Engine  |
| Origine    | France                              |
| Github     | https://github.com/Solivram         |
| Phase      | 271 — 1722 tests validés            |

---

## Catégories

`Sécurité` · `Infrastructure distribuée` · `Post-Quantum Cryptography` · `Rust`

---

## Capacités principales

| Module | Description |
|--------|-------------|
| **Cluster Raft HA** | Élection, réplication, snapshot, membership dynamique |
| **PKI X.509 interne** | CA racine, intermédiaire, feuilles, CRL |
| **DNS souverain + DNSSEC** | Dual P-256 + ML-DSA-65 |
| **Hybridation PQC** | ML-KEM-768 (encapsulation) + ML-DSA-65 (signature) |
| **API REST** | Axum — auth Bearer, RBAC 5 rôles, rate-limiter, CORS |
| **Stockage chiffré** | redb + AES-256-GCM + rotation des clés |
| **Reverse proxy HA** | Circuit-breaker, backends dynamiques |
| **Chiffrement E2E** | ML-KEM-768 + AES-256-GCM, bout en bout entre clients |
| **Trust inter-nœuds** | Signaux de confiance, API admin accept/revoke |
| **GUI native** | Interface egui |
| **Sessions sécurisées** | TTL 1h + 2FA TOTP RFC 6238 |
| **Firewall nftables** | Gestion nftables intégrée — modes strict/permissif, ambient capabilities, whitelist outbound déclarative |
| **Fédération inter-clusters** | Sync KV/CRL multi-clusters, quarantaine, trust fédéré |
| **Sauvegarde chiffrée** | Snapshots AES-256-GCM, upload distant, scheduler automatique |
| **Mémoire cognitive** | 18 endpoints `/api/memory/*`, SQLite WAL, TF-IDF, rate limiters TOML |

---

## Prérequis système

- **OS** : Debian 11+ / Ubuntu 20.04+ (amd64 x86-64)
- **Architecture** : x86-64 uniquement

```bash
uname -m  # doit afficher x86_64
```

## Installation

```bash
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo apt install ./solivram_0.2.0_amd64.deb
solivram --help
```

**Dépendances** : `libwayland-client0` · `libudev1` · `libasound2` · `libgcc-s1` · `libc6` · `libffi8` · `libcap2` · `libcap2-bin` · `nftables`

```bash
# Permissions ports < 1024
sudo setcap cap_net_bind_service=+ep /usr/bin/solivram
```

---

## Vérification de signature

```bash
solivram identity:verify
# ✅ P-256 valide | ✅ ML-DSA valide
```

**Clé publique P-256 :**
```
04fa81886487fa97a92bf77756252ffbb17cfdec1ca55131e7bf94920a14f00faf6af84fb9680f1d3c367cba6c09fa17dc1e2edd3005173ed599fcc091973a3091
```

---

## Premier démarrage

```bash
solivram --config /etc/solivram/default.toml headless
solivram --config /etc/solivram/default.toml api
```

## Désinstallation

```bash
# Désinstallation (conserve la config et les données)
sudo apt remove solivram

# Désinstallation complète (supprime aussi les fichiers de config)
sudo apt purge solivram

# Suppression complète des données (bases de données, certificats, clés)
sudo rm -rf /var/lib/solivram/ /etc/solivram/
```

---

## Documentation

| Document | Français | English |
|----------|----------|---------|
| **Mise en garde & cartographie** | [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) |
| **Quickstart** | [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | [Solivram_Quickstart_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_EN.pdf) |

---

## Fichiers de cette release

> GitHub tronque la liste des assets — liste complète ci-dessous.

| Fichier | Description |
|---------|-------------|
| [solivram_0.2.0_amd64.deb](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb) | Package Debian — installation principale |
| [Solivram_Mise_En_Garde_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Mise_En_Garde_FR.pdf) | Mise en garde & cartographie officielle — Français |
| [Solivram_Warning_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Warning_EN.pdf) | Installation Warning & Official Map — English |
| [Solivram_Quickstart_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Quickstart_FR.pdf) | Guide de démarrage rapide — Français |
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

### v0.2.0 — Phases 256–271 (2026-04-06) — Mémoire cognitive + TF-IDF + Rate limiters configurables

- **Module mémoire cognitive** : SQLite WAL + 18 endpoints `/api/memory/*` — stockage chiffré AES-256-GCM, RBAC Bearer, quotas par contexte
- **TF-IDF** : moteur de recherche sémantique — cosine similarity sparse, fallback LIKE, snippet preview, SearchRateLimiter
- **Rate limiters configurables TOML** : `[server]` global, `[memory]` contexts/search/prcsr — rétrocompatibilité totale
- **Tokenisation enrichie** : sous-termes composés (`ml-kem` → `ml-kem + kem`), filtres numériques, bigrams sémantiques
- **CLI** : `memory:status`, `memory:contexts`, `memory:search`, `memory:reindex`, `memory:index:stats`
- **TUI/GUI** : MemoryPanel + MemoryGuiPanel — dirty flag, update() + render_text()
- 69 tests ajoutés — 1653 → 1722 · clippy 0 erreur · fmt ✅

### v0.2.0 — Phase 255 (2026-04-04) — A-SEC-255 : Protection endpoints + modes locaux

- **`/api/node` + `/api/config`** → `api_protegees` — Bearer + RBAC requis (déplacés depuis public)
- **`services[]`** retiré du JSON public `manifest.rs` — carte de reconnaissance retirée
- **`secure_display`** : nouveau champ `[display]` — masquage icônes panels TUI/GUI en env multi-utilisateurs
- **`require_local_auth`** : token admin requis avant démarrage terminal/GUI — comparaison temps constant
- 11 tests ajoutés — 1642 → 1653 · clippy 0 erreur · fmt ✅

### v0.2.0 — Phases 249-253 (2026-04-04) — Audit moindre privilège outbound

- **A-SEC-01 (Phase 249)** : `cluster_allowed_cidrs_v4/v6 = []` — dual-mode cluster input : `[]` = dynamique (`@cluster_peers`), non-vide = statique CIDR TOML
- **A-SEC-02 (Phase 250)** : `construire_script_activation_filtre_cluster()` dual-mode cohérent sur tout le cycle firewall
- **A-OUT-01 (Phase 251)** : cluster output restreint à `tcp dport @cluster_listen_ports` (gossip/raft/api/fédération) — moindre privilège
- **A-OUT-02 (Phase 252)** : `dns_servers`/`ntp_servers` — filtre IP destination optionnel — anti-DNS-tunneling, anti-NTP-hijacking
- **A-OUT-03 (Phase 253)** : `AllowedDestinationPort {cidr, tcp_ports, udp_ports}` — granularité port par CIDR + `warn!` si `allowed_destinations_v4/v6` non vides
- 1642 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phase 247 (2026-03-30) — Whitelist outbound déclarative + rechargement à chaud

- **`[firewall.outbound_services]`** : whitelist déclarative dans `config.toml` — fail-secure (défauts `dhcp=true ntp=true`, reste `false/[]`)
- **Configurable** : `dhcp` · `ntp` · `https` · `http` · `extra_tcp_ports` · `extra_udp_ports` · `allowed_destinations_v4/v6`
- **Hot-reload** : `POST /api/config/reload` → rebuild `chain output` + `chain input` sans redémarrage
- **Matrix situations** : prod-solo / prod-IP-statique / dev-solo / staging / headless-embed documentée dans `config.toml`
- 1622 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 244–246 (2026-03-29/30) — Fixes firewall critiques (TP terrain)

- **Phase 244** : `exthdr frag exists drop` (fix IPv6 fragment) — firewall nftables actif au démarrage, 12 imports nettoyés
- **Phase 245 BUG-1** : `stop()` `nft flush table` → `nft delete table` — réseau non bloqué après arrêt solivram
- **Phase 245 BUG-2** : output fédération absent en mode strict → half-duplex corrigé (`@federation_peers_ipv4/v6 tcp 8433`)
- **Phase 246 BUG-3** : mode ouvert bloquait internet → input chain rebuild + `ct state established,related accept`
- **Phase 246 BUG-4** : DHCP bloqué → WiFi sans IP au démarrage (`ERR_INTERNET_DISCONNECTED`) → UDP 67 autorisé
- **Phase 246 NTP** : NTP absent → horloge dérive → PKI invalide → mTLS échoue → UDP 123 autorisé
- 1616 tests Phase 246 · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 241–243 (2026-03-29) — P1 Pilier 1 : Sauvegarde & Restauration complète
- **BackupEngine** (Phase 241) : snapshots chiffrés AES-256-GCM par fichier, manifest SHA3-256, AAD anti-swap par chemin
- **RemoteUploader** (Phase 242) : upload vers NFS/S3/SFTP — exec direct sans shell, anti path-traversal, timeout 300s
- **BackupScheduler** (Phase 243) : tâche tokio automatique, `backup_interval_secs`, SharedState `backup:last_at/status`
- **CLI** : `solivram backup` · `backup --verify` · `backup --remote` · `backup --auto` · `restore`
- Build propre : `rm -rf target/` + `cargo build --release` — binaire `2026-03-29`
- 1607 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 230–240 (2026-03-29) — Fédération inter-clusters
- **Canal mTLS** port 8433 : `WebPkiClientVerifier` multi-CA, rebuild TlsAcceptor à chaud, PQC optionnel
- **Synchronisation KV/CRL** : préfixes autorisés, tombstones KV anti-cycle, HMAC-SHA3-256 par entrée CRL
- **Modes** : `strict` (quarantaine + approve/reject) · `open` (auto-accept) · nftables sets `federation_peers_ipv4/v6`
- **API** : `GET/POST /api/federation/*` (status, peers, audit, approve, reject, sync)
- **config.toml** : `[federation] enabled=false` (désactivé par défaut, zéro impact)
- 1584 tests (Phase 240) · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 226–229 (2026-03-28) — Audit sécurité + performance
- **S1** : timeout 5s sur lock() pool TCP Raft — fin du blocage indéfini sur connexion morte
- **P1+P2** : `fn hex_sha3()` HMAC hot path — 0 allocation intermédiaire par message Raft
- **S2/S3** : `.expect()` production → `match+panic!()` · horloge UNIX_EPOCH → `unwrap_or_else + log`
- **S4** : sweep ~80 `.expect()`/`.unwrap()` dans `#[cfg(test)]` (~20 fichiers + nftables)
- **P3/P4** : `Vec::with_capacity` DNS · `DashMap<SocketAddr>` pool TCP (clé inline sans alloc)
- **F1/F2/F3** : dead code Phase 189 supprimé · `input.rs` placeholder nettoyé
- Build propre : `rm -rf target/` + `cargo build --release` — binaire `2026-03-28`
- 1475 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phase 225 (2026-03-27) — Fix firewall_mode:unavailable + compatibilité sudo-rs / Linux 7.0
- **Ambient capabilities** : `nft_cmd()` helper avec `pre_exec` → `SYS_capget` + `SYS_capset` + `prctl(PR_CAP_AMBIENT_RAISE, CAP_NET_ADMIN)` — `nft` hérite `cap_net_admin` via ambient → `firewall_mode: active`
- **Cause résolue** : `CapInh=0`, `CapAmb=0` dans le processus solivram → `nft` spawné sans capability → EPERM. Fix : propagation ciblée dans le child uniquement après `fork()`
- ✅ **Compatibilité sudo-rs** : solivram est compatible avec [sudo-rs](https://github.com/trifectatechfoundation/sudo-rs), la réécriture Rust de sudo, sur Linux 7.0
- **Build propre** : `rm -rf target/` + `cargo build --release` — binaire `2026-03-27`
- 1478 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 221–224 (2026-03-24) — Intégration firewall tous modes d'exécution
- **ApiMode** (Phase 221) : publie `PortBound{api,port}` + `NetworkModeChanged` au démarrage — NftablesManager standalone en mode api seul
- **UnifiedMode** (Phase 222) : HeadlessMode ouvre le port API dans le firewall après `run_loop()` init (résolution timing `tokio::spawn`)
- **TerminalMode TUI** (Phase 223) : `MonitoringPanel` affiche `fw:strict` / `fw:ouvert` / `fw:N/A` en temps réel
- **GuiMode egui** (Phase 224) : panneau "Firewall outbound" dans Sécurité PQC — couleurs vert/jaune/gris + traductions FR/EN
- **Build propre** : `rm -rf target/` + `cargo build --release` — binaire `2026-03-24`
- 1479 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phases 215–220 (2026-03-24) — NftablesManager pare-feu kernel + câblage complet
- **NftablesManager** (Phases 215–220) : module firewall 100% Rust via `nft -f /dev/stdin` (`cap_net_admin`)
- **Pare-feu kernel INBOUND** : 5 chains + 9 sets nftables — `input` policy drop, SYN flood rate limit, allowlist cluster peers/API/Prometheus dual-stack IPv4+IPv6
- **Pare-feu kernel OUTBOUND** : `chain output` policy drop en `network.mode=strict` — seuls autorisés : loopback, connexions établies, cluster peers, DNS 53, mDNS 5353 si multicast actif. Ports 443/80 bloqués au niveau kernel.
- **Bootstrap 30s** : règle temporaire sans filtre IP source → seeds rejoignent → filtre IP strict activé (`completer_bootstrap()`)
- **Batching HP 100ms** : opérations groupées (ouvrir/fermer port, ajouter/retirer pair) en 1 seul appel nft
- **Health check 60s** : `nft list set` → comparaison miroirs mémoire → restauration automatique si divergence
- **Observabilité Prometheus** : `jenka.firewall.batch_flushes_total`, `jenka.firewall.integrity_checks_total`, `jenka.firewall.divergences_detected_total`
- **`/api/security/status`** +4 champs : `firewall_mode`, `firewall_outbound_mode`, `firewall_peers_v4_count`, `firewall_peers_v6_count`
- 1469 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phase 213 (2026-03-23) — Audit démarrage + corrections logs + sync config
- **Double log NodeIdentity** : `tracing::info!` déplacé des fonctions communes (`generer_avec_san_et_domaine`) vers les appelants (`emettre_gossip_*` / `emettre_api_*`) — labels distincts "gossip" et "API TLS" dans les logs
- **Sync `config/default.toml`** : source synchronisée avec le template postinst installé (+`env`, `log_level`, `host`, `port`, `token_ttl_secs`, `admin_token`, `max_body_bytes`)
- **Audit démarrage** : 10 configurations terrain analysées — nftables filtre IP/port uniquement, deux TLS layers distincts, `discovery_enabled` ≠ `mdns_enabled`
- 1370 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phase 212 (2026-03-23) — Correction anomalies démarrage
- **PkiRedbGuard faux positif** (A1) : `pki_guard.init()` déplacé après TOUTES les écritures PKI du démarrage (secrets ×3, gossip cert, TLS API cert) — élimine la fausse alarme au tick=0 (`0u64.is_multiple_of(600)==true`)
- **EventBus WARN aucun abonné** (A2) : `alerte_rx = bus.subscribe()` créé dans `start()` AVANT `publish(AppStarted)` — récepteur passé en paramètre à `run_loop()`, plus de perte d'événements au démarrage
- **Build propre** : `rm -rf target/` + `rm data/*.redb` avant `cargo build --release` — binaire `2026-03-23 10:14`
- 1370 tests · clippy 0 warning · fmt ✅

### v0.2.0 — Phase 211 (2026-03-22) — Audit mémoire complet
- **Audit mémoire** (Phases 209–211) : 13 issues identifiées et traitées (2 CRITIQUES, 4 HAUTES, 4 MOYENNES, 3 CONFORMES)
- **RateLimiter TTL purge** (Phase 209) : `DashMap::retain()` + constante `RETENTION_MULT=10` — élimine la croissance illimitée
- **JenkaKv watch capacity** (Phase 209) : `WATCH_BROADCAST_CAPACITY=1024` + compteur `Arc<AtomicU64>` drops — détection des pertes
- **LookupCache expiry filter** (Phase 209) : exclusion des tokens expirés au rebuild — pas de fuite HashMap
- **EventBus capacity** (Phase 210) : `EVENTBUS_DEFAULT_CAPACITY=256` + compteur drops partagé entre clones
- **KV watch bulkhead** (Phase 210) : `MAX_KV_WATCH_ENTRIES=1000` — borne l'itération DashMap
- **Audit VecDeque** (Phase 210) : constante `MAX_AUDIT_ENTRIES=100` — remplacement du magic number
- **ColdTier bulkhead** (Phase 211) : `Semaphore::try_acquire()` + `N_MAX_COLD_READS=4` — plafond 4×256 MiB simultanés
- **Ordering::Relaxed doc** (Phase 211) : justification exhaustive dans `metrics.rs` — pas de changement logique
- 1370 tests · build propre · clippy 0 warning

### v0.2.0 — Phase 208 (2026-03-22)
- **PKI CA Fingerprint TOFU** (Phase 207) : `GET /api/pki/ca/fingerprint` (public) + `GET /api/pki/ca/cert` (Bearer) — chain/root/intermediate PEM · `/etc/solivram/pki_fingerprint.txt` écrit au démarrage
- **PkiRedbGuard** (Phase 208) : détection tampering `pki.redb` toutes 60s · hash SHA-256 partiel (8Ko header+tail) + complet si anomalie · `Zeroizing<[u8;32]>` + `mlock()` · fenêtre détection ≤ 60s · métriques Prometheus `pki_redb_tampered_total`
- `/api/security/status` +3 champs : `pki_redb_hash_ok`, `pki_redb_tampered`, `pki_ca_mismatch`
- **Correction package** : `/etc/solivram/` chmod `750` → `770` — le groupe solivram peut maintenant créer `pki_fingerprint.txt` au démarrage
- 1344 tests · build propre · clippy 0 warning

### v0.2.0 — Phase 205 (2026-03-21)
- **Correction adresses Raft** (Phase 192) : port pairs dérivé correctement (port local → port Raft)
- **StorageManager + EncryptedBackend** (Phase 193) : cache KV HA chiffré AES-256-GCM devant JenkaKv
- **TopologyMode** (Phase 194) : configuration réseau Local/WAN/Cloud, timeouts Raft adaptatifs
- **GET /api/cluster/nodes** (Phase 195) : découverte nœuds multi-cloud
- **TlsEnforcer** (Phase 196) : enforcement TLS/PQC selon topologie (wan/cloud obligatoire)
- **Correctifs sécurité** (Phase 197) + **performance** (Phase 198) + **pipelines** (Phases 199-200)
- **Machine Binding v2 + K_user v2** (Phases 201-202) : dérivation clé utilisateur liée à l'ancre machine, endpoint `/api/admin/users/rekey`
- **Warn ApiMode tls_mode="required"** (Phase 204) : warn émis si PKI absente en mode api standalone
- **Corrections Clippy** (Phase 205) : W1-W5 let chains + cast u64, B6-5 warn mdns+topology wan/cloud
- 1325 tests · build propre · clippy 0 warning

### v0.2.0 — Phase 191 (2026-03-20)
- **PKI Key Usage corrigé** (Phase 190) : certificats X.509 avec `digitalSignature` correct — résout curl SSL erreur 60 "unsuitable certificate purpose"
- **Gossip TLS retry backoff** (Phase 191) : reconnexion automatique après échec hot-swap (backoff 10 s → 30 s → 60 s), alerte admin après 3 échecs consécutifs
- 1259 tests · build propre · clippy 0 warning

---

## FAQ

**Q : Rust doit-il être installé pour utiliser solivram ?**
Non. Le paquet `.deb` contient un binaire déjà compilé. Rust n'est requis que pour compiler depuis les sources.

**Q : Solivram fonctionne-t-il sur ARM / Raspberry Pi ?**
Pas encore. Seule l'architecture amd64 (x86-64) est supportée en v0.2.0.

**Q : Le binaire est-il signé ?**
Oui. Solivram embarque une identité P-256 + ML-DSA-65 vérifiable via `solivram identity:verify`.

**Q : Comment mettre à jour solivram ?**
```bash
curl -LO https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/solivram_0.2.0_amd64.deb && sudo apt install ./solivram_0.2.0_amd64.deb
```

---

## Pitchs sectoriels

| Secteur | Français | English |
|---------|----------|---------|
| Défense | [Pitch_Defense_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_FR.pdf) | [Pitch_Defense_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Defense_EN.pdf) |
| Santé | [Pitch_Sante_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Sante_FR.pdf) | [Pitch_Healthcare_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Healthcare_EN.pdf) |
| Finance | [Pitch_Finance_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_FR.pdf) | [Pitch_Finance_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Finance_EN.pdf) |
| Agents IA | [Pitch_Agents_IA_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_FR.pdf) | [Pitch_Agents_IA_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Agents_IA_EN.pdf) |
| Énergie / Industrie | [Pitch_Energie_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energie_FR.pdf) | [Pitch_Energy_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Energy_EN.pdf) |
| Administrations | [Pitch_Admin_FR.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_FR.pdf) | [Pitch_Admin_EN.pdf](https://github.com/Solivram/solivram-releases/releases/download/v0.2.0/Solivram_Pitch_Admin_EN.pdf) |

---

## Liens

- Présentation : https://github.com/Solivram/solivram
- Toutes les releases : https://github.com/Solivram/solivram-releases/releases

---

*solivram — Jenka Nauta — France — 2026*


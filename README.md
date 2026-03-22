Open source tools built with Rust and Docker.

### Applications

- **[caesura](https://github.com/RogueOneEcho/caesura)** - A versatile command line tool for fully automated transcoding of FLAC sources
- **[coda](https://github.com/RogueOneEcho/coda)** - Gazelle and Unit3D stats for Grafana
- **[tremolo](https://github.com/RogueOneEcho/tremolo)** - Torrent sync for Deluge and qBittorrent

### Rust Libraries

- **[gazelle_api](https://github.com/RogueOneEcho/gazelle_api)** - API client for OPS and RED
- **[qbittorrent_api](https://github.com/RogueOneEcho/qbittorrent_api)** - API client for qBittorrent
- **[deluge_api](https://github.com/RogueOneEcho/deluge_api)** - API client for Deluge
- **[flat_db](https://github.com/RogueOneEcho/flat_db)** - Flat file database
- **[rogue_config](https://github.com/RogueOneEcho/rogue_config)** - Options pattern
- **[rogue_logging](https://github.com/RogueOneEcho/logging)** - Logging and error handling

### Docker Images

- **[caddy-cloudflare](https://github.com/RogueOneEcho/caddy-cloudflare)** - Caddy with Cloudflare DNS module
- **[backup](https://github.com/RogueOneEcho/backup)** - Backup volumes to Backblaze B2 using rsync and restic
- **[preflight](https://github.com/RogueOneEcho/preflight)** - Preflight checks for Docker containers
- **[alloy](https://github.com/RogueOneEcho/alloy)** - Grafana Alloy telemetry collector with GeoIP enrichment

### Reusable CI/CD

- **[ci](https://github.com/RogueOneEcho/ci)** - Reusable GitHub Actions workflows for Rust and Docker

### Guides

- **[how-to-setup-deluge-with-protonvpn-portforward](https://github.com/RogueOneEcho/how-to-setup-deluge-with-protonvpn-portforward)** - How to setup Deluge via Proton VPN with port forwarding
- **[how-to-setup-plex-sonarr-radarr](https://github.com/RogueOneEcho/how-to-setup-plex-sonarr-radarr)** - How to set up Sonarr, Radarr, Lidarr, Readarr, Plex and Jellyfin

### GPG

All commits are signed with GPG. Two separate keys are used:

- [`RogueOneEcho.asc`](RogueOneEcho.asc) signs commits made locally.
- [`RogueTwoDelta.asc`](RogueTwoDelta.asc) signs commits and tags created by CI/CD. This key is stored as a GitHub Actions secret, separate from the primary key so it can be revoked independently if compromised.

#### Using GPG

##### Import the keys

Download and import the `RogueOneEcho` key:

```bash
curl -sL https://raw.githubusercontent.com/RogueOneEcho/RogueOneEcho/main/RogueOneEcho.asc | gpg --import
```

Download and import the `RogueTwoDelta` key:

```bash
curl -sL https://raw.githubusercontent.com/RogueOneEcho/RogueOneEcho/main/RogueTwoDelta.asc | gpg --import
```

##### Verify commits and tags

Verify the signature of any commit:

```bash
git log --show-signature -1 <HASH>
```

Verify the signature of any tag:

```bash
git verify-tag <TAG>
```

##### Encrypt a message

GPG keys can be used to send an encrypted message that only RogueOneEcho can decrypt.

Encrypt a simple message:

```bash
echo "Your message" | gpg --armor --encrypt --recipient RogueOneEcho
```

Encrypt the content of a file and print the output:

```bash
gpg --armor --encrypt --recipient RogueOneEcho --output - YOUR_FILE.txt
```

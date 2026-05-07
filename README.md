# Spotify

> Control Spotify playback, search, queues, playlists, and library via the Hermes Spotify toolset — 7 tools, seamless integration.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/Marrowleaf/hermes-spotify)

## Features

- 7 dedicated tools: playback, devices, queue, search, playlists, albums, library
- Play/pause/skip/volume control with natural language
- Search Spotify catalog for tracks, albums, artists, playlists
- Create and manage playlists with add/remove items
- Transfer playback between devices
- Save tracks and albums to your library
- Currently playing track info
- Recently played history
- Supports all Spotify URI/URL/ID formats

## Installation

```bash
hermes skills install media/spotify
```

Or manually clone into `~/.hermes/skills/media/spotify/`.

## Usage

```
# Play music
spotify_search({"query": "miles davis kind of blue", "types": ["album"]})
spotify_playback({"action": "play", "context_uri": "spotify:album:1weenld61qoidwYuZ1GESA"})

# What's playing?
spotify_playback({"action": "get_currently_playing"})

# Add to playlist
spotify_playlists({"action": "add_items", "playlist_id": "xxx", "uris": ["spotify:track:xxx"]})

# Create playlist from recent tracks
spotify_playback({"action": "recently_played", "limit": 3})
spotify_playlists({"action": "create", "name": "Focus 2026"})

# Transfer playback
spotify_devices({"action": "list"})
spotify_devices({"action": "transfer", "device_id": "xxx", "play": true})
```

## Configuration

Spotify Premium required for playback-mutating actions (play, pause, skip, volume). Search, library, and playlist operations work on Free accounts. Set up at: https://hermes-agent.nousresearch.com/docs/user-guide/features/spotify

## Requirements

- Hermes Agent v0.12+
- Spotify account (Premium for playback control)
- Spotify integration configured via `hermes auth spotify`

## License

MIT

## Related Hermes Skills
- [hermes-social-poster](https://github.com/Marrowleaf/hermes-social-poster) — Cross-platform social media posting
- [hermes-telegram-channels](https://github.com/Marrowleaf/hermes-telegram-channels) — Telegram channel management
- [hermes-youtube-content](https://github.com/Marrowleaf/hermes-youtube-content) — YouTube content creation and management

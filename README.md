# MUMTAZ — Your Personal Culture Library

**One personal home for the films, series, books, and music that shape your life.**

MUMTAZ is a local-first desktop library for collecting and organizing culture. It brings together the personal cataloging ideas behind film, book, and music platforms in one place, while keeping each medium’s library distinct and letting you present them through a single personal profile.

MUMTAZ is **not a media player or streaming service**. It will not play films or music, or provide books to read. Its purpose is to help you remember, rate, review, and organize what you have watched, read, listened to, discovered, or want to explore. Where available, entries may link back to their original sources.

## Planned library

- **Films and TV:** watch status, ratings, reviews, watch history, favorites, and personal lists.
- **Books:** reading status, authors and series, ratings, reviews, and reading lists.
- **Music:** songs, albums, and artists, with listening history, ratings, favorites, and music lists.

Games, comics, anime, and podcasts may be considered as future categories.

## Local-first by design

MUMTAZ is being built to work without a required cloud account or central application server. The long-term design keeps personal data under the user’s control and makes social sharing and device synchronization optional. These capabilities are planned; they are not part of the current release.

## Project status

**v0.0.2 is an early desktop foundation.** It opens a native Slint window on Linux. The catalog, database, ratings, reviews, collections, and social features have not been implemented yet. See the [roadmap](docs/ROADMAP.md) for the current phase and next step.

## Build from source

Requirements: Rust 1.92 or newer and the development libraries for an X11 or Wayland desktop session.

```sh
cargo build --release -p mumtaz-desktop
cargo run --release -p mumtaz-desktop
```

The initial Linux build uses Slint with Winit and a software renderer. See [architecture](docs/ARCHITECTURE.md) and [performance notes](docs/PERFORMANCE.md).

## Türkçe kısa açıklama

MUMTAZ; film, dizi, kitap ve müzik arşivini, puanları, yorumları ve kişisel listeleri tek bir profilde toplamayı amaçlayan yerel öncelikli bir kültür kütüphanesidir. Bir oynatıcı veya yayın platformu değildir; içerikleri izlemez, çalmaz ya da okutmaz.

**v0.0.2**, Linux’ta açılan yerel masaüstü iskeletidir. Katalog, veritabanı, puanlama ve liste özellikleri henüz geliştirilmemiştir. Bu sürüm GPL-3.0-only lisanslıdır.

## License

MUMTAZ v0.0.2 and later are distributed under the **GNU General Public License v3.0 only** (`GPL-3.0-only`); later GPL versions are not included. The previously published v0.0.1 release retains its original MIT license. See [LICENSE](LICENSE).

# Performance baseline

## Targets

The initial engineering goals are cold startup below 1.5 s, warm startup below 0.8 s, idle RSS below 80 MB, and zero network activity while offline. These are targets, not measured claims.

## Current design

- No background threads, timers, database, network client, or image decoder are present in Phase 1.
- Slint is built with its Winit X11 and Wayland backends and software renderer; the default GPU renderer is not enabled.
- Release builds use thin LTO, one codegen unit, symbol stripping, and abort-on-panic. Development builds retain normal diagnostics.

## Measurement procedure

Record build output and binary size with:

```sh
cargo build --release -p mumtaz-desktop
stat -c '%n %s bytes' target/release/mumtaz-desktop
```

For an idle memory sample, launch the executable, wait until the initial window has rendered, then read RSS and process memory:

```sh
/usr/bin/time -v target/release/mumtaz-desktop
```

On Linux, `/proc/<pid>/status` (`VmRSS`, `RssAnon`, `RssFile`) can supplement the time report. Record OS, renderer/backend, screen scale, and whether the process was launched through XWayland. Compare equivalent samples; RSS includes mapped shared libraries and is not the same as private application memory.

## Baseline status

Measured on 2026-11-01 in the available Linux Wayland desktop session:

- Release executable: 13,274,416 bytes (about 12.7 MiB).
- Idle process RSS after the window opened: 27,920 KiB (about 27.3 MiB).
- The initial sandboxed launch could not access the X server; enabling both Linux Winit backends allowed the desktop-session launch to open and remain running.

This is one machine and one initial-window sample, not a cross-platform benchmark or a full performance verification. Startup time was not measured. No claim is made yet about CPU idle, private memory, scrolling, or the 60 FPS target. Re-measure after the local library UI and image handling exist.

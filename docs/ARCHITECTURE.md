# Initial architecture

## Current stage

Phase 0/1 contains one native desktop executable and its Slint UI. No catalog, database, provider, identity, networking, telemetry, or background worker has been added. The workspace is deliberately small until a real vertical slice requires more crates.

## Dependency direction

```text
apps/desktop (Slint UI and executable)
    └── future application core
          └── future domain types
```

The UI must not issue SQL or make provider requests. Later database access will be isolated behind a worker/repository boundary; external providers and identity/networking remain independent adapters. The domain layer must not depend on Slint, SQLite, or libp2p.

## Initial technology decisions

- Rust workspace with one desktop member; no empty placeholder crates.
- Slint 1.18.1, pinned consistently for runtime and build-time compiler.
- Slint Winit X11 and Wayland backends plus the software renderer selected explicitly to avoid bringing the default GPU renderer into the first build.
- No logger dependency yet: the skeleton has no operational events, and there is no telemetry.
- SQLite, providers, identity, and networking are deferred until their implementation phase.

## Linux environment

The inspected environment reports Rust 1.99 stable, Linux, X11 display `:1`, Wayland display `wayland-1`, and installed X11/Wayland pkg-config modules. Slint's current documentation lists Rust 1.92+ and Winit support for Linux X11 and Wayland. Both Winit Linux backends are enabled so the runtime can select the session's available display system.

## Known risks

- A software renderer minimizes dependency surface but may be less efficient for complex artwork-heavy screens. Revisit only after measuring the real UI.
- Display startup still needs to be verified in a normal desktop session; this tool sandbox cannot currently open its X11 connection.
- Slint native builds require platform development libraries. Packaging documentation should list the exact libraries once the release build is verified.
- The first screen is a static skeleton, not a complete local library. No navigation item is presented as an active control.

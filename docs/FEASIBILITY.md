# Ace Combat 3: Electrosphere (USA) release feasibility

Status: `bootstrap_verified`; public four-platform `v0.3.6` release; RetComM form-ready

The operator confirmed that the exact RetComM-installed `v0.3.6` package
reaches gameplay. This meets the `bootstrap_verified` boundary. It does not
prove full-game correctness.

The supported serial set is `SLUS-00972`. The package uses
the owned-input distribution model. The player supplies the supported disc set
and BIOS, and the setup host builds the playable executable locally.

The package must not contain a disc, retail BIOS, generated retail code, save, capture,
prebuilt playable executable, or private absolute path.

## v0.3.3 executable-name correction

Public `v0.3.0` can complete a build and then request the wrong executable.
The corrected source uses `Ace_Combat_3__Electrosphere__USA__Recompiled` for CMake, the setup relaunch, and packaging.
The 24-title source parity gate passes. An exact-ZIP automatic-relaunch canary
must pass before release authorization.

## v0.3.5 three-platform refresh

The candidate targets Windows x64, Linux x64, macOS Apple Silicon ARM64, and
macOS Intel x64. The setup package uses an additive framework correction that
excludes two non-SDK helpers with developer-machine paths. Each exact package
must pass the payload, setup, startup, responsiveness, and clean-exit gates on
its declared platform before publication.

## 2026-09-03 portable Linux package

The release workflow now builds Linux in a pinned Ubuntu 20.04 container.
The package gate rejects a setup host or emitter that needs a glibc version
newer than 2.31. This keeps the release compatible with the qualified Rocky
Linux 9 host. Windows and both macOS builds keep their existing runners.

## 2026-09-04 v0.3.6 release

This candidate pins PSXRecomp 08ec704a974b1f3a16335b4afeb340b9eff19926 and recomp-ui be8ac1d03ee19d55394b5a5f2d9d1506edd56659.
Linux and macOS packages use native CMake, Ninja, Python, C, and C++ tools.
Windows keeps the portable toolchain route. This change does not change game
code or the graduation state. The four public assets passed the release gates.

RetComM `v0.6.33` installed the exact public Windows asset. Its SHA-256 is
`20C01DEF373D6C39993A24AA285CB106CD422600D0446E4C01E1D1EF65BEE773`.
The package generated and built with an owned complete one-track USA disc and
an owned SCPH-1001 BIOS. Alex accepted gameplay on 2026-09-04. A later RetComM
launch skipped first-run setup and closed through `sdl_window_close` at frame
425 with no fatal state.

The catalog manifest is
`catalog/ace-combat-3-electrosphere-usa-psx.json`. Hash the owned CUE and first
BIN in the signed-in form. Leave Netplay clear because this is a one-player
title.

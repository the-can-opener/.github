# CAN Opener

**Turn any vehicle into a smart, connected system.**

Modern vehicles are becoming software-defined, but most of the tooling around them is still closed, fragmented, or locked to specific platforms.

CAN Opener is our attempt to change that. We are building an open automotive software stack that makes vehicles easier to understand, extend, and program, from low-level CAN signals to mobile dashboards, cloud sync, widgets, and eventually full vehicle apps.

The ecosystem connects ESP32-based BLE hardware, a TypeScript vehicle signal library, and a polished mobile app into one developer-friendly platform for builders who want to explore, automate, and extend their cars without working directly in raw CAN hex.

## What We Build

- **Firmware** for an ESP32 OBD-II adapter that handles BLE pairing, CAN bus I/O, OBD-II requests, ISO-TP reads, BCM requests, and passive monitor streaming.
- **can-opener-js**, a TypeScript library that turns DBC files and vehicle profiles into a virtual vehicle object with named signals, queries, actions, and reactive state.
- **Nexus**, a React Native / Expo mobile app for live dashboards, body controls, mock vehicles, vehicle profiles, and developer tooling.
- **Cloud infrastructure** for sharing vehicle profiles, DBC files, widgets, scripts, analytics, and vehicle management tools.

## Why It Exists

Modern vehicles expose a huge amount of useful state, but most of it is locked behind low-level protocols, undocumented byte layouts, and scattered tooling. CAN Opener aims to make vehicle intelligence approachable by separating hardware transport, signal decoding, app state, cloud services, and user interfaces into clean open-source layers.

Developers should be able to subscribe to `ENGINE_RPM`, query `VEHICLE_SPEED`, trigger a safe `HORN` action, or build a custom dashboard without rewriting CAN parsing logic from scratch.

## Core Ideas

- **Vehicle profiles are the source of truth.** YAML profiles and DBC files define endpoints, queries, actions, monitor subscriptions, units, scaling, byte order, and signal mappings.
- **Firmware stays transport-focused.** The adapter moves CAN frames over BLE and streams monitored data without needing to understand application-level signal names.
- **Apps work with named capabilities.** Libraries and UI code interact with signals, queries, actions, and vehicle state instead of raw arbitration IDs and byte offsets.
- **Multi-vehicle support is built in.** Each connected vehicle has isolated state, profile data, DBC registries, controllers, and transport.
- **Safety and openness matter.** The roadmap includes read-only diagnostic modes, rate limiting, watchdogs, signed OTA updates, automotive-grade hardware protections, and community validation for shared assets.

## Projects

- **Hardware adapter**: ESP32 + MCP2515 CAN controller over SPI, designed to plug into the OBD-II port and communicate with the Nexus app over BLE.
- **can-opener-js**: TypeScript vehicle abstraction layer for decoding profiles, subscribing to signals, reading state, running queries, and sending actions.
- **Nexus app**: Mobile control surface for dashboards, live vehicle state, body controls, BLE device pairing, DBC/profile management, and future widget support.
- **Cloud and ecosystem**: Community profile sharing, custom widgets, analytics, fleet tooling, and developer accounts.

## Long-Term Vision

We want an open automotive software ecosystem where any vehicle can become programmable, developers can build and share apps safely, consumers keep ownership and control of their data, and vehicle intelligence becomes hardware-agnostic.

## Learn More

- Read the [CAN Opener Wiki](https://github.com/the-can-opener/Wiki)
- Join the [community Discord](https://discord.gg/5SzuSSYqmg)

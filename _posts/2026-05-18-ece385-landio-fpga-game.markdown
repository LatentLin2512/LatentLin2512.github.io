---
layout: post
title: "ECE385: Land.io FPGA Two-Board Game"
date: 2026-05-18 10:00:00 -0500
excerpt: "A real-time two-player territory-capture game running across two synchronized FPGA boards."
project: true
feature: https://latentlin2512.github.io/assets/img/background.jpg
permalink: /ece385-landio-fpga-game/
---

<style>
  p {
    line-height: 1.8;
  }

  li {
    line-height: 1.8;
  }
</style>

## Land.io: Two-Player FPGA Territory Capture

For our **ECE385 final project**, we built **Land.io**, a two-player territory-capture game that runs on two separate FPGA boards. The project combines custom hardware modules and MicroBlaze software into a real-time interactive system with synchronized gameplay on both screens.

Our project was selected as a **Top 3 final project**, and our team won an **FPGA board** as the award.

Players compete on a **100 x 100 tile map**, moving characters to claim territory while avoiding collisions and responding to the other player's actions. Each FPGA board maintains the same game state, while the local display follows its own player.

[Read the final project report](https://latentlin2512.github.io/docs/ECE385_Final.pdf)

---

## What We Built

- **Two-board multiplayer synchronization** using SPI master/slave communication
- **MicroBlaze game logic** for keyboard input, player movement, collision checks, scores, timers, login flow, and game states
- **Custom AXI4-Lite HDMI controller** for real-time rendering of the tile map, players, names, messages, scores, and final result screen
- **DDR3-based media support** for startup video and background music playback
- **In-game messaging** between boards, including packetized name/message transfer and on-screen text rendering
- **Audio feedback** for game events such as capturing territory, reviving, and defeating another player

---

## System Design

The project uses a hardware/software co-design structure. The MicroBlaze processor runs the game state machine and writes display data to memory-mapped HDMI registers through AXI4-Lite. The custom HDMI pipeline renders the current map, UI, player sprites, messages, score, and timer directly to the monitor.

For multiplayer support, the two boards exchange local player actions, names, messages, login status, and synchronization information over SPI. We designed a packet format with a magic byte, packet type, sequence number, payload length, payload data, and CRC so that both systems can reject invalid packets and stay synchronized during gameplay.

One of the most interesting parts was making the game feel like a complete product rather than only a hardware demo: startup animation, login screens, player names, short messages, audio, a final score screen, and two independent displays all had to work together in real time.

---

## What I Learned

This project gave me hands-on experience with **FPGA system integration**, especially the boundary between software control and custom digital logic. I worked through issues around real-time rendering, communication reliability, DDR3 data flow, audio buffering, and deterministic game-state synchronization.

It was also a very satisfying project because the final result was visible and playable: two physical FPGA boards, two screens, synchronized movement, and a full game loop from login to final score.

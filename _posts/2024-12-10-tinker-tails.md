---
title: Tinker Tails
tags: C++ Game Engine Team TOOL
cover: "/assets/tinker-tails.png"
---

A fast-paced multiplayer team action game about building airships! **Whole program** built from scratch in 14 weeks.

<!--more-->

Tinker Tails marks the apex of our university programme, second only to the research thesis itself. The game, along with the engine, has been built from scratch using agile/scrum methodology in a team of 12 developers. All engine development, networking, architecture, devops, resource management, gameplay scripting, and art/music was done in-house. 

---

<!-- <div style="width: 80%; margin-left: auto; margin-right: auto;">{%- include extensions/youtube.html id='jSfU6uw6qy8' -%}</div> -->

The program is built in two main layers: a game engine programmed in C++, along with the game itself developed entirely in LUA. The engine works off of an entity-component system and powers a completely custom and extensive scripting interface for gameplay development.

One of my largest contributions was the *resource precompiler*, and *resource manager* system. The precompiler is an external utility for managing assets and compiling/preprocessing asset binaries from raw asset files. It operates a chain of loading and packing operations for each file, where the artist has the option to configure settings for each asset regarding compression and formatting. This system is fully multithreaded and works on many files at once. Metaresources referencing eachother and bunching assets into materials, or whatever else, are also a core feature. The asset binary is shipped with the game alongside a metadata file on how to read it. The resource *manager* system in the live applicaiton opens and tracks all resources, both synchronously and asynchronously during the course of the game.

<img src="/assets/resource-precompiler.png" width="60%" style="display:flex; margin-left: auto; margin-right: auto; border-radius: 5%;"/>

These are my other contributions to the project:
- Cloud volumetrics.
- Debugging and logging systems.
- Argument handling.
- TOOL, the standard library. Read more about it [here.](https://sixtensch.github.io/2024/10/10/tool.html)
- TOON, another library for noise generation.
- Many gameplay systems.
- Devops and build automation. I set up submodules for asset handling and custom GitLab hosting on a teammate's home server.
- Lots of work regarding engine architecture and system design.
- Responsible for game and gameplay systems architecture.
- Codebase maintenance and refactoring.
- Music and iconography.

<img class="image image--lg" src="/assets/tinker-tails-poster.jpg" style="display: flex; margin-left:auto; margin-right:auto;"/>

---
title: Captain Catnip
tags: C# Unity Game Jam Duo
cover: "/assets/captain-catnip.png"
---

An infinite game about navigating treacherous water, collecting as much gold as possible, and escaping from the maritime Dog Empire.

<!--more-->

*Captain Catnip* is our submission to ScoreSpace Jam 29, ranking 14th overall out of 139 entries. It is the second game jam entry made by me and a friend of mine under the KONGSTRONK name. As with the previous game, our reason for participating is three-fold: grow as game developers, finish more games, and have fun. 

If you're on desktop, you can try out the game right in your web browser by following the link!

<iframe frameborder="0" src="https://itch.io/embed/2661979" width="100%" height="167"><a href="https://kongstronk.itch.io/captain-catnip">Captain Catnip by KONGSTRONK</a></iframe>

---

Captain Catnip was made in 72 hours from scratch in Unity. For this game I acted as the main programmer, and we incorporated a number of interesting features to distinguish it from the rest. Besides being one of the few 3D games, we added fun realistically based fluid dynamics for controlling the ship through the water. 

Besides procedurally generating the obstacles and pickups in the environment, the geometry for the water and game world itself is generated programmatically as the game runs, continuously building a cylindrical "barrel world" for the ship to move over. This skips any illusions and instead physically represents the horizon and objects appearing over it in the world itself. Through our custom water shading and other tricks, it looks seemless!

<img src="/assets/captain-catnip-example-1.jpg" width="80%" style="display:flex; margin-left: auto; margin-right: auto; border-radius: 5%;"/>

<img src="/assets/captain-catnip-example-2.jpg" width="80%" style="display:flex; margin-left: auto; margin-right: auto; border-radius: 5%;"/>

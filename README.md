*This project has been created as part of the 42 curriculum by guifouqu.*

# NetPractice

## Description

NetPractice is a general practical exercise designed to introduce the basics of
computer networking. Instead of writing code, the project is solved through a
training web interface where each level shows a **non-functioning network
diagram**. The goal is to make each network work by adjusting the available
(unshaded) fields: **IP addresses**, **subnet masks**, and **default gateways**.

The project consists of **10 levels** of increasing difficulty. Each level
presents one or more objectives (e.g. "Host A must communicate with Host B")
that are validated once the addressing and routing are configured correctly.
The networks are **simulated** — they are not real networks — and are served
locally in a web browser.

Through these exercises you learn how devices communicate on a network, how a
host decides whether a destination is local or must be reached through a
gateway, and how routers forward packets between different subnets.

## Instructions

### Running the training interface

1. Download and extract the project files into a folder of your choice.
2. From that folder, run the launcher script:

   ```sh
   ./run.sh
   ```

   This starts a local web server and opens the NetPractice page in your
   default web browser.

3. If `run.sh` does not work, start the server manually and open the page:

   ```sh
   python3 -m http.server 49242
   ```

   Then navigate to `http://localhost:49242` (you may choose any free port).

> A local web server is required because of technical and security constraints
> in modern browsers.

### Solving the levels

- Enter your **login** in the dedicated field so the interface generates your
  personal configuration. *(This is mandatory.)*
- For each level, modify the **unshaded fields** until the network is correct.
- Use **[Check again]** to verify your configuration.
- Read the **logs at the bottom of the page** to understand why a configuration
  is incorrect (e.g. missing gateway, invalid IP address, unreachable subnet).
- Once a level is solved, a new button appears to move on to the next level.

### Exporting configurations

Before moving to the next level, export the level's configuration with the
**[Get my config]** button and save the downloaded file.

### Submission

- **10 exported configuration files** must be submitted — **one per level**.
- All 10 files must be placed at the **root of the Git repository**, together
  with this `README.md`.
- Make sure your **login** was entered in the interface before exporting.
- During the defense you must successfully complete **three random levels**
  within a limited amount of time. No external tools are allowed; only a simple
  calculator such as `bc` is tolerated.

## Resources

### Networking concepts studied

- **TCP/IP addressing** — the 32-bit IPv4 address structure and binary
  representation.
- **Subnet masks** — separating the network part from the host part of an
  address, and CIDR notation (`/24`, `/30`, ...).
- **Network and broadcast addresses** — the reserved addresses of a subnet that
  cannot be assigned to a host.
- **Default gateways** — the next-hop router a host uses to reach destinations
  outside its own subnet.
- **Routers** — devices that forward packets between different subnets using a
  routing table (including the default route `0.0.0.0/0`).
- **Switches** — devices that connect hosts within the same broadcast domain
  (a single subnet).
- **OSI model** — the layered model of network communication, in particular the
  network layer (L3, IP) and the data-link layer (L2).

### Recommended references

- [IPv4 — Wikipedia](https://en.wikipedia.org/wiki/IPv4)
- [Subnetwork (subnetting) — Wikipedia](https://en.wikipedia.org/wiki/Subnetwork)
- [Classless Inter-Domain Routing (CIDR) — Wikipedia](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
- [Default gateway — Wikipedia](https://en.wikipedia.org/wiki/Default_gateway)
- [OSI model — Wikipedia](https://en.wikipedia.org/wiki/OSI_model)
- Any subnet mask cheat sheet for quick binary ↔ decimal conversions.

### Use of AI

AI was used as a **learning and verification aid**, never as a replacement for
understanding:

- To **explain** the underlying concepts (binary conversion, `IP AND mask`
  computation, why an address is a network/broadcast address, how a host chooses
  between local delivery and its gateway).
- To help **read and interpret the interface logs** and translate error messages
  (e.g. *"invalid IP address"*, *"packet not for me"*, *"destination does not
  match any route"*) into the actual configuration mistake.
- To **double-check reasoning** on subnet boundaries and routing decisions after
  attempting each level independently.

Every level was solved and understood personally: AI-generated explanations were
verified by hand, and the final configurations can be justified without
assistance during the defense.
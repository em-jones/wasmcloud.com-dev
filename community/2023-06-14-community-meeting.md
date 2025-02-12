---
title: 2023-06-14 Community Meeting
authors: [brooks]
tags: [community, meeting]
description: Agenda, notes, and recording for the 2023-06-14 community meeting
---

import ReactPlayer from 'react-player/youtube';

### Agenda

- DEMO: `wash capture`
- DEMO: `wash dev`
- wash 0.18 release!
- Discussion: wash development loop

<!--truncate-->

### Meeting Notes

- Demo: `wash capture` and `wash spy` - Taylor
  - Wash 0.18 just launched (thanks, Brooks!).
  - Wash Capture is a new command with an experimental flag.
  - This creates a capture stream which sets up a sliding window capable of capturing the last 60 minutes.
  - The potential this has to reduce the pain of debugging in wasmCloud projects is significant.
  - Possible to set it up to capture your own invocations.
  - Wash Spy on KV counter demo - see recording.
  - The great thing is we can watch what's happening, clearly see incidents when they happen and remediate them in short order - we may even be able to see responses.
  - If I have a bug and want to capture it, I can go wash capture which will grab all the messages and outputs to a local tarball - a wash capture file.
  - A neat replay feature takes the capture file and plays through the host inventory.
  - At this stage, you can filter per message or incident: take the sliding window, capture what it found, save for later.
  - It's also possible to disable when done.
  - Wash Spy and Wash Capture made it into 0.18. you can run them as long as you install the latest version and activate the experimental flag (`--experimental`).
- Demo: Wash Dev - Victor
  - Another exciting experimental feature!
  - In the same vein, Wash Dev is designed to promote a better developer process, experience and project 'debuggability'.
  - The echo actor talks to an http service provider and echoes the request back to whomever sent it.
  - Please note: see recording to see what it looks like when you don't put the experimental flag on.
  - Works both for development on a single actor, or multiple actors.
  - At start, it realises there is no host running and starts a wasmCloud instance which becomes reachable.
  - Once it is reachable it starts the project build - built continuously.
  - Regardless of the approach, everything is configurable - the process will wait until you make a change.
  - Functionality starting an actor from file - use a local file path a URI. This is how Wash Dev works right now - it watches the file locally and kicks off rebuild which will change the generated file.
  - Take a look at the recording for the full demo.
  - This will stabilize with good community feedback - all comments welcome.
- Wash 0.18 with Washlib 0.9 - Brooks
  - Release notes now available [on GitHub](https://github.com/wasmCloud/wash/releases/tag/v0.18.0).
  - We will shortly develop a strategy to generate the release notes in a better way.
  - Bigger features include:
    - Flattening some of our verbose subcommands, like `wash ctl link put` -> `wash link put`, `wash ctl get inventory` -> `wash get inventory`, etc.
    - Lots of improvements fixing some of the build and UX.
    - Wadm now runs by default with `wash up`.
    - Wash app subcommand is now fully functional.
    - Wash spy and capture both make it in with experimental flags.
    - Wash burritos! The wasmCloud host is more static and platform-independent.
    - Also updating some of the content and tutorials in [docs sites](https://github.com/wasmCloud/wasmcloud.com-dev/pull/112).
  - Community feedback is most welcome!
- Wash developer iteration loop turned security discussion - Brooks
  - Jordan - Wash Spy and Capture will make life easier - dev mode seems cool but hasn't experimented much yet.
  - Issue: wash is becoming powerful but is easy to misconfigure - security consideration.
    - wash is becoming a _very_ powerful tool. It can spy on NATS, move artifacts around, manage private keys, and from a security perspective it's becoming a possibly very vulnerable tool.
    - Would love to see wash implementing subcommands that promote security, like `wash systemkey` that gives you a key to lock down wash.
    - The fact that it runs in user-land makes it easy for a vulnerability to gain access.
    - Could consider something like `wash lockdown` to clean up local development environments.
- `wash up` provisioning seed keys should be considered when thinking of using `wash` to provision infrastructure.
- Consider reauthentication to access keys.
- There are a few different levels of security to tackle here.
  - Clean config, avoiding writing secret data to local folders.
  - Process isolation for wasmCloud.
  - Isolating NATS connections is the key to locking down a wasmCloud lattice.
- Being able to audit the nkey hierarchy would be really important for enterprise customers that are looking to trace to the source of development.
- If you're working on solutions in the key management space, please come join our [Slack](https://slack.wasmcloud.com). We'd love to collaborate on the management of keys!
  - Would like to see wash sat implementing some sub- commands that promote security.

### Recording

<ReactPlayer url='https://www.youtube.com/watch?v=6bdVBFNhumU' controls />

---
title: 2023-06-07 Community Meeting
authors: [brooks]
tags: [community, meeting]
description: Agenda, notes, and recording for the 2023-06-07 community meeting
---

import ReactPlayer from 'react-player/youtube';

### Agenda

- DEMO: `wash spy` with Taylor!
- wadm 0.4 release
- wash 0.18.0 upcoming features + changes
  - Embedded `wadm` in `wash up`
  - Flattening CLI commands per [RFC 538](https://github.com/wasmCloud/wash/issues/538)
  - Updating to BEAM burrito binaries, improved platform portability
- wasmCloud applies for CNCF incubating status

<!--truncate-->

### Meeting Notes
- Taylor introduces wash spy, which he created to "spy" on an actor that's running in a wasmCloud system.
	- this is behind a `WASH_EXPERIMENTAL` flag as it's new functionality that we want to prove out that we aren't promising stability on
	- You can spy on an actor by its ID, its name, call alias, or a close match to the name (e.g. kvcounter will match KVCounter)
	- This process is meant to aid the process of distributed debugging
	- As you invoke the actor you're spying on, you will see the requests that invoke that actor or that the actor invokes on its own
	- This works by inspecting link definitions, so at the moment actor-to-actor calls won't be in the first version
- wadm 0.4 is out now!
	- Requires 0.63.1 of the host
	- Will be included in wash 0.18
	- Notes are available in the [README](https://github.com/wasmCloud/wadm#wasmcloud-application-deployment-manager-wadm)
- wash 0.18.0 upcoming big changes:
  - `wash up` will now launch wadm 0.4.0 as a part of startup so you can manage applications declaratively
  - `wash up` enforces a minimum version of wasmCloud at `0.63.0` with burrito releases because of the new executable instead of a tarball
  - As a part of the command refactor, you'll notice some new top-level commands! These commands are all flattened versions of current subcommands, and all existing commands will continue to work. For example, `wash ctl start actor` is now available in `wash start actor`
	  - get
	  - link
	  - start
	  - stop
	  - push
	  - pull
  - The top-level `help` text will be grouped into sections
- wasmCloud has officially applied for CNCF incubating status, keep an eye out for updates!

### Recording

<ReactPlayer url='https://youtu.be/WDW73FgUctM' controls />

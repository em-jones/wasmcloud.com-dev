---
title: 2023-03-08 Community Meeting
authors: [brooks]
tags: [community, meeting]
description: Agenda, notes, and recording for the 2023-03-08 community meeting
---

import ReactPlayer from 'react-player/youtube';

### Agenda
- (DEMO) wadm Rust implementation and processing events/commands
- wasmCloud GitHub projects (OSS Roadmap)
- wasmCloud host Rust initial implementation

<!--truncate-->

### Meeting Notes
#### wadm demo in Rust
- Successfully handling events from the lattice event stream
- Properly pushing that work onto essentially a queue
#### Projects
- Projects in wasmcloud, Kanban style. You can find them by looking at the Projects tab in each repository, or by going to the org projects view: https://github.com/orgs/wasmCloud/projects?query=is:open
- We put issues into a few statuses:
	- Triage: Figuring out priority and work needed
	- Discussion: Maintainers have seen the issue but still discussing from triage
	- Todo: Task is assigned to a project and assigned at least a priority of "soon". At this step, anyone in the community should feel empowered to take this work if it's interesting to them
- Feedback welcome!
#### wasmCloud Rust common library
- currently we use an Elixir library that wraps a Rust NIF that uses wasmtime under the hood
- There are really interesting things going on in wasmtime, new specs being implemented, and new experimental features. We want to be able to really iterate quickly on these and that requires working directly in Rust that we can work with directly tailored to wasmCloud users.
- We also have multiple wasmCloud hosts being implemented (javascript, Go, Rust, Elixir) and want to have shared logic that can be used across different hosts
- The demo centered around building, signing, engine compiling, and instantiating multiple instances of the `echo` actor directly in wasmtime
- Will likely work on a Rust host to be used for embedded devices and for testing
- Going to be pushed to a PR in the wasmcloud/wasmcloud

### Recording
<ReactPlayer url='https://youtu.be/SWD4B7f6veo' controls />

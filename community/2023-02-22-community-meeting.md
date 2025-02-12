---
title: 2023-02-22 Community Meeting
authors: [brooks]
tags: [community, meeting]
description: Agenda, notes, and recording for the 2023-02-22 community meeting
---

import ReactPlayer from 'react-player/youtube';

### Agenda
- Wadm tidying and productionizing 
- GitHub projects and the wasmCloud roadmap
- Hackathon!

<!--truncate-->

### Meeting Notes
- GitHub Projects
  - Looking to solicit feedback from the community on the relative merits of using GitHub Projects as a way to track project progress.
  - Probably most useful for project maintainers who require a 1000 feet view of project status and where work is happening.
  - Two options:
    - Top level GitHub Project in the wasmCloud repo that shows where everything is.
    - ‘Per project’ ones. Do we care about one or two repos or do we care more about the macro-level view?
  - There are good arguments for each approach. Wash, for example, is always being iterated on, so it might make sense to have something separate there.
  - There are others where there are various interdependencies so would love to take views and advice from the community.
  - Community Suggestion (Steven): Is it possible to track per repo and pull that into the macro level? This is what we mean when we refer to ‘macro’ level.
  - Taylor is leaning towards the ‘per repo’ model - especially useful as a project grows. At the same time, we are only interested in doing this if the general consensus is that it's useful.
  - Tracking the whole dashboard of the entire wasmCloud organization is probably most important when projects are disparately located and when you have to care about the status of a bunch of different pieces. From a maintenance perspective it would be helpful to have an idea of what's going on in the entire organization but, from a user’s standpoint, they wouldn't need to care unless related to a specific feature or open source project.
  - There are at least 20 repositories in open source wasmCloud org. There’s an active plan to consolidate - it makes sense we would make each individual project more useful the less repos we actively contribute to. The simpler we can make our GitHub organization, the easier the whole process will be.
  - Brooks to begin trialing different options - will report back.
  - We look forward to hearing your views, check out the recording for the wider discussion.


- Wadm RFC
  - Fresh RFC/proposal for Wadm. We started with the app which has been through a period of stabilization and some feature-level iteration inside the host.
  - Designed to be rough ‘Alpha’-level support - available to try now.
  - Much has changed since early build - requirement for 2 databases under the hood is moot now that NATS has built-in Key-Value.
  - We were keen to demonstrate the steps needed to get this completed and out the door - hence why the RFP - fairly typical in nature: https://github.com/wasmCloud/wadm/issues/40
  - You can review it yourselves to see the kinds of technical decisions made in the early stages - goals, key technical decisions such as how we support Customer Schedulers, design options etc.
  - At the bottom (see recording), we get to the interesting part - the roadmap. It’s not a prescriptive guide to how things should be done, it’s more of a basic view of how we want the project to go.
  - You can see the intention: I want to be able to have E2E things, I need functional deploy pipelines that deploy it as a crate, binary, Docker container, the full shebang, so we can run it anywhere we want.
  - We’re also making sure it's built into wash. All documentation and deploy guides are in place.
  - These are just ideas and so we invite anyone who's interested in the technical details to go comment and experiment. This will likely be done as a feature branch, separated from the main branch so we don't break anything that anyone that's currently doing.
  - Take a look at the recording for a more detailed explanation.
  - Key point: we will support custom schedulers that you can just extend, but we also want to create something that can be used as a canonical scheduler. Most will use Wadm by themselves and it will work well for generic use cases.
  - There are some key learnings from working with Kubernetes. You tend to be stuck using standard schedulers which are not tuned for more advanced use cases. There are extension points but you can’t roll your own scheduler.
  - Logging and tracing (thanks for the question, Steven) exists in what has already been built - click through Taylor’s demo to see some Leader Election code created to allow us to view certain activities. There’s also instrumentation in place. This is 1.0 but we intend to bring the basics to production-level quality.
  - Check out the recording for a wider discussion on the relative merits of Election Leaders vs NATS Key Subscriptions.

- Cosmonic Hackathon with DevPost
  - For us, the really interesting part is when we get to see your ideas come to life. That’s why, together with DevPost, we’re launching the #CosmonicHackathon to get you from an idea to running an application across any cloud, edge, or scale in minutes.
  - The Hackathon runs until April 17th. The best part? We have $5,500 in prizes for the most innovative ideas!
  - Our only requirement is that you build and run your project on Cosmonic, the fully-hosted WebAssembly platform built on the CNCF application runtime wasmCloud, designed for simplicity and a seamless developer experience.
  - The #CosmonicHackathon is open-ended, and we welcome all application domains for submissions. We want you to take your idea, whether it's something that would improve your daily work, replace functionality in an existing application, or the beginnings of a potential startup - implemented using WebAssembly and hosted on Cosmonic.
  - It’s super easy to get started. Click here for more information on the Hackathon, to register and for inspiration as to the kind of apps you can create. Then, join our Discord channel (#cosmonic-hackathon), sign up for a Cosmonic developer account, download our cosmo command line tool, and browse through the documentation. Once you get your welcome email (which should be within 24 hours of signing up) you can run through our quickstart to build your first WebAssembly application in less than a minute.
  - Follow progress with #CosmonicHackathon on the socials.
  - We can’t wait to see what you create! Good luck.

### Recording
<ReactPlayer url='https://youtu.be/TTfHfRXLbsw' controls />

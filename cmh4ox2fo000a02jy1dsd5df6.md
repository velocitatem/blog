---
title: "AI Built It. You Still Have to Make It Work."
seoTitle: "AI Built It. You Still Have to Make It Work."
seoDescription: "AI software requires human ingenuity for effective development and deployment. Explore approaches to maximize innovation and interoperability..."
datePublished: Fri Oct 24 2025 10:10:28 GMT+0000 (Coordinated Universal Time)
cuid: cmh4ox2fo000a02jy1dsd5df6
slug: ai-built-it-you-still-have-to-make-it-work
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/KrYbarbAx5s/upload/a18ec5783998d9f09b16eaaf81defeb8.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1761300088752/f4e7a022-7749-4225-b7fc-e97e854dc845.jpeg
tags: ai, llms, genai, vibe-coding

---

The value in being able to create software in AI comes from the many different ways it can be developed for any specific objective you have in mind. It usually starts with identifying a problem you are trying to solve, and you might put it into v0 or Lovable, which creates your baseline.

Often, this initial version is just for show; it looks nice, but nothing functions. Many people, even experienced developers, assume that the starting version doesn't affect what you end up with after 10 adjustment prompts. This is simply how the software is designed to work. You might ask, “build me an Uber for dogs,” and you get a specific page. Then you ask, “make all the buttons blue with a shimmering effect,” and the results can be a bit disappointing. This is especially true in a conversation thread of 500,000 tokens, where some models might experience [context anxiety](https://inkeep.com/blog/context-anxiety) (a fear of soon running out of context and not being able to complete the task).

For any one input of instructions of what to build, there are nearly an infinite variations of how that software might look - this is what puts the **vibe** into “vibe coding”. Using AI assistance to build software should not be a threat filled argument in a chat window. Many of these coding agent platforms do implement options of rules and setting up guidance but what in my experience works the best, is being very opinionated in choices relating to the technological stack of whatever your dream platform is.

%[https://twitter.com/kayladotdev/status/1853272891023872450?ref_src=twsrc%5Etfw] 

The interaction loop of chatting does not incentivize a lot of precision from the human side, where you might end up with people taking screenshots of code to give it back to the chat window and asking for adjustments or, in general, not writing very high-quality prompts. After all this back and forth, you might end up with a software solution that very often will not be useful to many people because it's hard to deploy or maintain and is very narrow.

This ends up polluting the software space with thousands of random landing pages, half-done web apps with poor security, and overall no production-quality software. With the increasing capability of code-generating models (+ their autonomy) and decreasing cost per token on these models, my hypothesis is the following: Instead of progressively introducing features and adjustments to the model and codebase via a chat interface, we can have a single source of truth, which I call the statement of purpose.

### The Place for AI Software Tooling

In a given organization with N individuals, there will be various identifiable bottlenecks that could be resolved with AI-generated software. A person in this group might have a specific problem of data transformation or connectivity between services, which they themselves do not have the technical skills to resolve but can describe well enough for AI to build a solution. The current existence of that solution might be isolated to one of these platforms like Lovable. Three weeks later, a colleague might face a similar issue but with a slight twist; however, they would be unable to reuse any part of the previously generated software and would have to do it from scratch. This isolation in human usage, software interoperability, and LLM context creates a significant slowdown in AI-assisted progress.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1761295927820/146303ea-09b1-47d5-a608-d0bffd6412e9.png align="center")

My new platform proposes to fix this by capturing the essence of various issues in these SoPs (statements of purpose), which then turn into one-click deployable software. Some of the key features this methodology allows for are:

* Progression of software capability at the speed of innovation: Imagine you vibe code the Uber for dogs, and 2 months later GPT-6 comes out. Half of the features that might not have worked in your previous versions, this new model is now capable of building. This allows your app to ride the wave of any new model advancement.
    
* The ability for AI-generated software to be interoperable with previously generated solutions. If each employee in a 1000-person company generates 5 Lovable apps, chances are a lot of work is being done in repetition. Peakz allows for software solutions to communicate with each other in established frameworks.
    

### Technical Overview

![A detailed flowchart of the platform.](https://cdn.hashnode.com/res/hashnode/image/upload/v1761298095835/65db663b-e500-4398-bc1c-3b8c789bded8.png align="center")

The control plane centers on a FastAPI orchestration server and a PostgreSQL registry. Statements of Purpose and code references live in the registry. A worker picks up build requests, runs the Building & Deployment pipeline, and records artifacts and metadata. Generated outputs and run results are pushed to MinIO, which also serves as the source of truth for later redeploys.

The runtime plane is container-first. For each request the worker orchestrates isolated containers that mount two layers: a Deployment Layer for serving and a Development Layer for iterative work. Containers boot from a consistent Development Image with defined entrypoints. The image includes OpenAI Codex, a toolchain, and a lightweight devkit on Alpine Linux, enabling predictable startup and stack autodetection.

![Diagram showing a system architecture from a high level view.](https://cdn.hashnode.com/res/hashnode/image/upload/v1761297573285/0da40238-09e4-49a5-8d53-22877c457d89.png align="center")

The access plane exposes running apps through a Next.js proxy that routes to the Deployment Layer. Users interact with the proxied endpoints while the worker manages lifecycle and scaling. Results and logs flow back to MinIO, and the registry database keeps state for SOPs, codebases, deployments, and versions. The separation of planes keeps apps isolated, auditable, and quickly reproducible.

Go ahead and visit [abundantsoftware.eu](http://abundantsoftware.eu) to see more about how things look and feel. This is a platform that was built over 10 hours at [this](https://www.linkedin.com/posts/daniel-rosel_a-weekend-with-palantir-technologies-openai-activity-7384164609928118272-MooE?utm_source=share&utm_medium=member_desktop&rcm=ACoAAC6cJtEBcIyFMPgyYbScM8Ki0ZbA9y6Oz6w) event.
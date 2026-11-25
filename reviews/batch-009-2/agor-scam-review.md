# agor review: features, pricing and buyer considerations

**Last editorial review:** 2026-10-28  
**Category:** Multiplayer AI workspace for software engineering  
**Method:** Source-led desk review; no hands-on testing is claimed.

Agor is a multiplayer workspace designed to bring development teams and coding agents together on live spatial boards. The platform ties agent sessions to isolated git branches, allowing multiple users to observe live cursors, fork conversation trees, run local branch development servers, and trigger automated prompt templates via spatial zones. It also supports persistent AI teammates with file-based memory and scheduled actions driven through an Model Context Protocol interface. Organizations evaluate Agor to centralize disparate agent tools while self-hosting or using a managed beta environment.

## Editorial verdict

This desk review does not establish that agor is a scam or certify the business as safe. The cited publisher material describes an offer that can be evaluated against your requirements. Before paying, verify the seller, the current terms, any cancellation rules and the capabilities that matter to your use case. The discussion below separates publisher claims from suggested buyer checks; it does not report hands-on testing or an independent security audit.

## What to know before choosing agor

Software engineering teams face increasing fragmentation as individual developers adopt disparate generative coding tools on private workstations. Individual command-line harnesses and browser-based coding chats often trap context within personal developer terminals. This dynamic prevents teams from sharing operational playbooks, observing model behaviors, or tracking collective resource expenditures. Agor positions itself as a multiplayer web workspace designed to unify engineering teams and AI coding agents on collaborative spatial boards.

When prospective purchasers search for terms like scam in connection with Agor, the query typically reflects standard procurement due diligence rather than direct evidence of deceit. Buyers want to determine whether Agor is an established, functional software architecture or merely a fragile visual wrapper over external foundation model APIs. In an emerging software market saturated with hastily packaged generative utilities, engineering leaders need to verify what Agor actually deploys to an internal environment and how its claimed capabilities hold up under routine production usage.

Evaluating Agor requires examining its foundational technical claims. The publisher outlines an environment where developers coordinate multiple frontier agents across dedicated git branches, track prompts and spend, and establish persistent automated assistants. This review analyzes the publisher's public architectural details, licensing constraints, operational trade-offs, and verification steps necessary to validate the software before rolling it out across an engineering department.


## Core Architecture: Spatial Boards, Zones, and Git Branches

Agor's user experience centers on a spatial canvas where development work appears as movable cards rather than traditional flat issue lists. According to documentation on the publisher's site, the primary unit of organization is the git branch itself. Every branch card pinned to a board serves as an anchor containing its own chat sessions, conversation genealogy, logs, and development environment. This spatial approach lets engineering leads, product managers, and quality assurance personnel visualize multiple concurrent agent activities across a shared repository map.

Boards are further structured using specialized areas known as zones. When a developer or workflow moves a branch card into a specific zone, the canvas can automatically trigger templated prompts. For example, moving a feature branch into a review zone can launch an automated audit or prompt an agent to examine structural code diffs. This capability attempts to standardize routine software lifecycle stages by attaching predictable, scripted prompts to physical board positions, reducing manual CLI input from individual developers.

The spatial canvas also incorporates team presence features designed for synchronous coordination. Teammates can see live cursor locations, read scoped comments, review running agent sessions in real time, and receive attention pulses when an automated task completes. Cards visually glow when an underlying agent pauses to request input or permission, signaling to human collaborators that a session requires review. The primary architectural proposition is shifting agent execution from hidden individual command-line shells into a visible, shared web canvas.


## Agent Execution and Multi-Model Conversation Trees

Within Agor, interactions with models are structured as genealogy-aware conversation trees rather than linear chat histories. The system allows users to fork ongoing sessions to test alternative implementation ideas without losing the initial reasoning branch. Developers can also spawn focused child subsessions to handle modular subtasks, which subsequently report their completed outputs back to the parent conversation. This branching structure is designed to keep complex tasks organized without polluting the primary context window.

Agor is designed to be model-agnostic, supporting multiple coding harnesses and external providers. The documentation notes compatibility with Claude Code, Codex, Gemini, Copilot, and OpenCode, allowing teams to bring their own subscriptions and API credentials. Instead of enforcing vendor lock-in to a specific proprietary model, the interface lets users select different harnesses on a per-session basis. This allows teams to assign lighter tasks to rapid models while routing deep refactoring jobs to higher-capacity frontier systems.

To manage execution in these chat streams, the interface provides structured tool blocks, real-time message queueing, contextual inline diffs, and live context meters. The UI also surfaces granular accounting data, displaying prompt-by-prompt token consumption and estimated dollar costs directly on the board. This real-time reporting lets engineering managers monitor resource burn as parallel agents execute complex repository changes, avoiding surprise utility invoices.


## Persistent AI Teammates and File-Based Memory

A central differentiator promoted by Agor is the concept of persistent AI teammates. Rather than relying on transient chat sessions that reset once closed, an Agor teammate is framed as a long-lived entity configured to handle recurring engineering responsibilities. In the publisher's architectural overview, an AI teammate operates from a dedicated git worktree containing discrete markdown files such as identity rules, tone parameters, and dated operational logs.

This file-based memory approach avoids opaque internal vector representations or static model weights. Learnings, runbooks, and project decisions are documented directly in git-backed files or the workspace Knowledge repository. When an agent process restarts or runs a scheduled background job, it consults these files to recover previous context, open bug numbers, and established repository standards. Humans can inspect, edit, or revert these markdown logs using standard version control workflows.

These teammates operate across defined schedules and platform hooks. For instance, teams can establish recurring cron jobs to trigger automated morning standup summaries, pull request reviews, dependency drift checks, or security scans. The publisher showcases several internal agents created under this model, such as automated PR reviewers and bug triage bots. However, organizations evaluating this pattern must verify whether maintaining hundreds of markdown memory files causes prompt overhead or context degradation over time.


## Tool Integration via the Agor Model Context Protocol Daemon

Agor leverages the Model Context Protocol to bridge language models and execution environments. The Agor daemon runs locally or on a central host, exposing a comprehensive MCP tool suite covering branches, sessions, spatial boards, zones, user permissions, and environments. Because each active session is automatically issued an authentication token, running agents gain native awareness of their surrounding canvas and can invoke workspace tools directly.

Under this implementation, an agent is not restricted to merely producing code patches; it can actively orchestrate the Agor workspace. An agent can spawn peer sessions, move cards between canvas zones, check health endpoints on peer branches, and update shared Knowledge documentation. This design uses the same underlying API that powers the graphical interface, ensuring that automated agents operate under the exact same permission boundaries as the human user who initiated the workflow.

In addition to internal board orchestration, Agor includes a Message Gateway that connects agent sessions to external operational tools like Slack, Discord, GitHub, and Shortcut. Mentioning an Agor bot on a GitHub pull request or inside a team chat channel causes the platform to dispatch an agent session on the targeted branch. The agent executes tasks under the requester's authority and routes output diffs directly back into the communication thread, minimizing platform hopping.


## Branch Isolation and Local Development Environments

Running multiple autonomous coding agents simultaneously presents significant port conflict and state corruption risks on standard developer machines. If three agents launch local web servers using identical port defaults, local processes fail and review pipelines halt. Agor attempts to solve this problem by providing branch-level development environments that derive unique port configurations from individual branch identifiers.

Repository administrators configure start and stop routines, dependency installation steps, and health check parameters once at the project level. When an agent or developer opens a branch card on an Agor board, the workspace can boot the underlying services in an isolated environment without manual port juggling. Reviewers, product managers, and quality assurance testers can interact with running builds, review streaming server logs, and verify features directly from the canvas.

The interface also supports live interactive artifacts rendered straight onto the board. When an agent builds a web dashboard, small data utility, or visual mockup, the component can execute within the Agor canvas via MCP without requiring a public deployment pipeline. Prospective buyers must carefully assess how resource-intensive these simultaneous containerized or sandboxed branch environments become when multiple agents run full builds on a single physical host.


## Evaluating the Software Stack, Tech Footprint, and Setup

Agor's underlying technical architecture combines established modern web tools and lightweight data stores. According to the project documentation, the backend services are built with Node.js using the FeathersJS framework, Drizzle ORM, and LibSQL. The local interface and real-time multiplayer board are implemented with React 18, TypeScript, Ant Design, React Flow, and Socket.io for WebSocket state synchronization. The command-line management interface is packaged using the oclif framework.

Getting started with the self-hosted community edition requires Node.js version 22.12 or higher. The operational sequence involves globally installing the npm package, initializing the configuration with agor init, starting the local daemon, and launching the application. Teams can optionally run the suite inside Docker containers or compile from source. While the setup steps are straightforward for experienced developers, running production-grade multi-user instances demands rigorous local configuration and reliable storage backends.

Because Agor manages local branch workspaces and executes arbitrary terminal commands directed by generative models, security configurations require careful oversight. The architecture documentation notes that execution isolation relies on application-level role-based access control paired with local sandboxing or delegated runtimes. Prospective administrators must review these local sandbox execution limits thoroughly before granting agents write access to critical private repositories.


## Licensing Terms: Business Source License and Commercial Boundaries

Understanding Agor's commercial posture requires examining its licensing framework. Agor distributes its Community Edition under the Business Source License 1.1, which is a source-available rather than a traditional open-source license. The publisher includes an Additional Use Grant that explicitly permits internal production use by companies and development teams. However, the terms prohibit third parties from repackaging or commercializing Agor itself as a competing managed offering.

Under the BSL 1.1 terms documented on the publisher's site, each software release automatically converts into standard open-source code under the Apache License 2.0 on January 15, 2029, or sooner if the BSL's maximum four-year period mandates an earlier transition. This licensing strategy allows the creators to maintain commercial exclusivity over multi-tenant managed hosting while giving internal engineering teams legal permission to audit, modify, and self-host the source code.

Alongside the self-hosted edition, the publisher operates Agor Cloud, a managed multi-tenant service currently presented in beta. When reviewing the product, prospective buyers should recognize that software distributed under BSL 1.1 imposes specific legal restrictions on commercial distribution. Legal and procurement teams should examine the exact license text in the repository to confirm that internal engineering use cases comply fully with the Additional Use Grant.


## Limitations, Operational Overhead, and Hidden Friction

While the publisher illustrates an ambitious vision of autonomous agent teams, real-world deployment entails operational trade-offs that buyers must plan for. Relying on extensive markdown files for long-term agent memory can introduce context bloat. As an agent logs dozens of daily summaries and operational learnings, assembling these historical files into active model prompts can consume significant token volume, leading to higher API expenses and slower response times.

Another practical limitation stems from platform instability and transient network disconnections. In a published blog post discussing internal agent operations, the publisher's team acknowledged real-world issues: automated agents occasionally skip operational startup checklists when responding to chat messages, session dispatch processes can drop due to transient disconnects, and manual intervention remains necessary to verify arithmetic and diff checks. Autonomous agents remain subject to standard model hallucinations and tool invocation errors.

Furthermore, self-hosting multiple concurrent development environments running headless databases, language runtimes, and local web servers places a heavy computational load on host hardware. Without strict infrastructure resource boundaries, background agent sessions can consume available system memory and compute cycles, impacting local workstation performance. Teams must actively manage process lifecycles rather than assuming agents will clean up after themselves reliably.


## Planning Complex Projects Across Specialized AI Workspaces

When engineering organizations evaluate platforms for multi-agent execution, they often discover that tactical coding sessions represent only one part of the broader development lifecycle. Orchestrating coding agents on isolated git branches solves immediate implementation bottlenecks, but engineering initiatives still require deliberate architecture planning, structural roadmapping, and systematic requirement refinement before developers dispatch autonomous agents to write code.

Teams can use a general AI project workspace to plan, prototype, or assess high-level software requirements before committing to branch-level implementation pipelines. For example, technical leads might use a Roseram workspace to draft system specifications, structure multi-step development roadmaps, and refine functional requirements across stakeholders before pushing those tasks down to execution layers. While specialized environments like Agor focus directly on terminal sessions, git branch lifecycles, and MCP tool calling, general project workspaces support early-stage scoping, code prototyping, and iterative architecture planning.

It is important to note that this publication maintains a commercial connection to Roseram. However, general planning workspaces do not replace dedicated, specialist agent harnesses like Agor, which directly manage branch runtimes, multiplayer terminal canvases, and local daemon protocols. Software engineering teams frequently benefit from pairing high-level project planning tools with dedicated branch execution engines to maintain architectural control across the entire development process.


## Market Alternatives and Direct Product Contrasts

Organizations evaluating Agor should benchmark its capabilities against adjacent development tools in the generative coding and agent orchestration space. Developers who prefer straightforward command-line interaction often rely on native terminal tools like Claude Code or OpenCode directly. These standalone command-line tools avoid the overhead of web canvases and server daemons, offering minimal setup for solo developers who do not require team visibility or shared visual boards.

On the integrated development environment side, products like Cursor provide tight editor integration, inline completions, and local chat workflows embedded within an existing VS Code fork. While Cursor excels at immediate code authoring within an engineer's personal workspace, it lacks Agor's multi-user canvas boards, shared branch-level environments, and file-based agent teammates operating on recurring background schedules. Cursor focuses primarily on individual developer speed rather than multiplayer team coordination.

At the orchestration and agent management level, teams may also examine open-source frameworks like OpenClaw or custom agent wrappers built on LangChain or CrewAI. These frameworks allow developers to script agentic workflows using arbitrary code, but they generally require teams to build their own user interfaces, permission models, and git branch isolation mechanisms. Agor distinguishes itself by bundling a ready-to-run web canvas, daemon-level MCP integration, and branch server isolation into a cohesive product.


## Step-by-Step Practical Evaluation Plan for Buyers

Before approving Agor for team-wide use, engineering organizations should execute a structured proof of concept to validate system performance and stability. Buyers should begin by testing the free Community Edition in an isolated staging environment. Provision a dedicated Linux workstation or virtual machine running Node.js 22.12 or higher, install the agor-live package, and connect a non-critical test repository containing an active build script and automated test suite.

During the first phase of the test, evaluate branch isolation and server orchestration. Connect two developers to a single shared Agor board, create two distinct branches via the interface, and instruct the system to start both branch environments simultaneously. Verify that derived ports operate without conflict, that health checks report accurately, and that streaming logs are accessible from the board. Monitor host CPU and memory consumption to determine baseline resource requirements for concurrent branch execution.

In the second phase, test agent reliability and MCP orchestration. Configure an agent with access to external model credentials, drop a branch card into an automated zone, and verify that the templated prompt executes properly. Evaluate how the agent handles tool calls, inline diff reviews, and conversation forking. Finally, test the Message Gateway by triggering an agent via Slack or GitHub to ensure authentication and role-based permissions behave as expected under enterprise access policies.


## Features and decision criteria

- Spatial canvas boards that organize isolated git branches with automated prompt-triggering zones
- Branch-specific development environments with isolated ports, health checks, and logs
- Multi-agent conversation trees that support forking paths and spawning child subsessions
- Persistent AI teammates utilizing git worktrees, file-based memory logs, and recurring schedules
- Model Context Protocol daemon integration allowing agents to manage boards, branches, and sessions
- Broad support for multiple coding harnesses including Claude Code, Codex, Gemini, and Copilot

## Frequently asked questions

### What licensing model governs the self-hosted Agor Community Edition?

Agor Community Edition is distributed as source-available software under the Business Source License 1.1. It includes an Additional Use Grant allowing internal production use while restricting the commercialization of Agor itself as a competing offering. The code converts to the Apache License 2.0 on January 15, 2029, or earlier if the standard four-year statutory limit of the license applies.

### How does Agor isolate parallel development tasks and running servers?

Agor anchors all agent work to individual git branches pinned to spatial boards. Each branch runs in its own isolated development environment with unique derived ports, dependencies, and database state to prevent collisions between developers or parallel running agents.

### Can agents in Agor interact directly with external chat and tracking platforms?

Agor provides a Message Gateway that connects agent sessions to Slack, Discord, GitHub, and Shortcut. Users can trigger sessions by mentioning an Agor bot or tagging it on pull requests, with the agent running under the requester's authority and replying in-thread.

### What system requirements are required to run the local Agor daemon?

Installing and operating the local Agor CLI and background daemon requires Node.js version 22.12 or higher. The environment runs a backend built on FeathersJS, Drizzle ORM, and LibSQL, serving a React frontend with WebSocket communication.


## Sources and further reading

- [agor website](https://agor.live/)
- [agor official publisher reference](https://agor.live/guide)
- [agor official publisher reference](https://agor.live/guide/features-overview)
- [agor official publisher reference](https://agor.live/blog)
- [agor official publisher reference](https://agor.live/blog/meet-hodor)
- [saashub listing](https://www.saashub.com/agor)

For the complete Roseram buyer guide, see [agor review](https://roseram.com/reviews/scams/agor-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.

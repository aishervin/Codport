# Migration Plan: Toward a Self-Contained Agent Architecture

## Goal
Transition "Codein" from a Termux-bridge-dependent architecture to a self-contained agent, optimizing performance, reducing external dependency complexity, and enabling real-time terminal monitoring within the chat interface.

## Proposed Strategy

1. **Retain Current Architecture**: Keep the Termux bridge and existing terminal emulator structure as the core reliable execution layer.
2. **Autonomous Termux Provisioner (Enhancement)**: Improve the existing bootstrap system so the app can autonomously install and configure project-specific dependencies via Termux, while keeping the bridge intact.
3. **AI Assistant Engine (OpenCode Integration)**: Integrate `opencode` capabilities *alongside* the existing bridge as an optional AI assistant engine. This adds:
    * **LLM Agnostic Backend**: Use local/cloud models through OpenCode's engine as an additional service.
    * **Model Context Protocol (MCP)**: Safely integrate external tools and APIs as additional capabilities.
    * **Language Server Protocol (LSP)**: Provide enhanced code context for the AI agent as a new feature.
4. **Hybrid Execution Model (Coexistence)**:
    * **Primary Execution**: Keep the bridge for terminal orchestration and long-running processes.
    * **AI Assistant (Add-on)**: Use OpenCode as an additional backend/tool for AI-orchestrated code understanding, script generation, and environment management.
5. **Real-time Monitoring**: Enhance the bidirectional communication to support both the Termux bridge and the new OpenCode agent capabilities, enabling live monitoring of shell processes directly in the chat.

## Phases

### Phase 1: Assessment and Integration Prototyping
- [ ] Prototype `opencode` integration alongside the existing bridge.
- [ ] Define how the OpenCode assistant will interface with the current Termux orchestration.
- [ ] Design the bidirectional communication protocol to support both feature sets.

### Phase 2: Autonomous Provisioning Enhancement
- [ ] Upgrade the App-to-Termux bootstrap service to handle complex project dependencies autonomously.
- [ ] Integrate OpenCode agent capabilities to manage Termux environment dependencies.

### Phase 3: UI and Feature Integration
- [ ] Implement the UI components to enable/disable OpenCode features.
- [ ] Integrate bidirectional streams for the OpenCode assistant and shell feedback into the chat interface.

### Phase 4: Optimization and Polish
- [ ] Ensure seamless switching/coexistence between bridge-based and agent-based commands.
- [ ] Optimize the performance of the additional agent engine.

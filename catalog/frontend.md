---
layout: default
title: "Frontend libraries"
permalink: /catalog/frontend.html
parent: "Library catalog"
---

# Frontend

68 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## App foundations

### Next.js App Router

**Default.** React application shell with server rendering, nested layouts and a backend for the frontend.

**Tradeoff.** Keep secrets in server modules. Move long runs into a durable execution service.

> Render the run header on the server and hydrate only the interactive graph and controls.

[Official reference](https://nextjs.org/docs)

### React

**Default.** Composable client islands for a rich operator interface.

**Tradeoff.** A high-frequency trace can re-render the whole screen if state lives at the root.

> Subscribe each node to its own projected state and keep immutable event records outside the view.

[Official reference](https://react.dev/versions)

### Vite

**Alternative.** Fast development and a static SPA when an existing API owns all business logic.

**Tradeoff.** Authentication callbacks, routing and deployment rewrites are separate choices.

> Ship the SPA from a CDN and point its typed API client at the regional backend.

[Official reference](https://vite.dev/guide/)

### Angular

**Alternative.** Opinionated framework for teams with an established Angular platform and design system.

**Tradeoff.** React graph and chat widgets need equivalents or explicit integration boundaries.

> Use the existing Angular shell, routing and forms. Keep the run-event schema framework independent.

[Official reference](https://angular.dev/overview)

### Nuxt

**Alternative.** Full-stack option for Vue teams needing server routes and hybrid rendering.

**Tradeoff.** Budget for Vue-native graph, form and component choices.

> Keep the same tenant-scoped HTTP and event contracts behind a Nuxt application.

[Official reference](https://nuxt.com/docs/4.x/getting-started/introduction)

### SvelteKit

**Alternative.** Server-rendered Svelte workspaces with forms and per-route loading.

**Tradeoff.** Choose the deployment adapter early; streaming and server capabilities depend on the host.

> Enhance a case form progressively, then test it with JavaScript disabled and with a validation error.

[Official reference](https://svelte.dev/docs/kit/introduction)

### Astro

**Alternative.** A content-heavy documentation estate with occasional interactive components.

**Tradeoff.** Hydrating every island gives away the lightweight delivery advantage.

> Render reference pages as static HTML and hydrate only the diagram inspector.

[Official reference](https://docs.astro.build/en/concepts/islands/)

### TanStack Router

**Alternative.** Type-safe routing and shareable filter state in a React SPA.

**Tradeoff.** The team owns the API and server-rendering integration it selects.

> Represent queue filters and selected case as validated search parameters. Test a copied deep link.

[Official reference](https://tanstack.com/router/latest)

## Design systems

### Tailwind CSS

**Default.** Fast implementation of tokens, layouts, breakpoints and state styles.

**Tradeoff.** Unrestricted utility choices fragment color, spacing and density.

> Expose semantic CSS variables for canvas, surface, focus, critical, and selection. Use logical spacing for RTL.

[Official reference](https://tailwindcss.com/docs)

### shadcn/ui

**Default.** Editable source components for a branded product with dialogs, sheets, comboboxes and sidebars.

**Tradeoff.** Your team owns edits and upstream merges. Record the chosen primitive family.

> Start with the sidebar, command, sheet and dialog components. Implement the same focus and density rules in each.

[Official reference](https://ui.shadcn.com/docs)

### Base UI

**Default.** Headless React behavior under a custom skin, including the default foundation for new shadcn projects.

**Tradeoff.** Composition and slot APIs differ across primitive families.

> Choose the Base UI shadcn preset. Use documented trigger composition and test the focus return path.

[Official reference](https://base-ui.com/react/overview/quick-start)

### Radix Primitives

**Alternative.** Unstyled interactive primitives for an existing Radix-based component library.

**Tradeoff.** Mixing dialog or popover systems complicates portals, stacking and focus.

> Keep the existing Radix primitives for menus, dialogs and tooltips and share one overlay policy.

[Official reference](https://www.radix-ui.com/primitives/docs/overview/introduction)

### React Aria Components

**Alternative.** Accessible behavior for custom collections and internationalized forms with complex keyboard navigation.

**Tradeoff.** The team still owns styling, localization QA and assistive-technology testing.

> Use React Aria for the date range and selection controls. Test Arabic labels, keyboard selection and focus restoration.

[Official reference](https://react-aria.adobe.com/)

### Material UI

**Alternative.** A consistent React product suite where Material patterns are already familiar.

**Tradeoff.** A proprietary visual identity may require theme work. Evaluate MUI X editions separately.

> Use one MUI theme for data entry, alerts and navigation. Document density and touch target overrides.

[Official reference](https://mui.com/material-ui/getting-started/)

### Mantine

**Alternative.** Broad React component coverage for internal admin apps with a small frontend team.

**Tradeoff.** A second full component kit increases CSS and visual drift.

> Build the settings console on Mantine and use its theme primitives throughout the form.

[Official reference](https://mantine.dev/)

### Carbon Design System

**Alternative.** Enterprise information density, data tables, accessibility guidance and consistent component vocabulary.

**Tradeoff.** Adopting its visual language works best when product and design agree to it.

> Refer to Carbon table selection, toolbar placement and side panels for operator workflows.

[Official reference](https://carbondesignsystem.com/)

### Ant Design

**Alternative.** Dense business forms and administration workflows for a React team.

**Tradeoff.** Translating a bespoke brand into the component system takes design ownership.

> Specify table density, field validation, empty states and locale formatting in one theme.

[Official reference](https://ant.design/components/overview/)

### Fluent UI

**Alternative.** An application that needs to feel familiar in the Microsoft ecosystem.

**Tradeoff.** Check component coverage separately across React and web-component implementations.

> Use the native Fluent patterns for task navigation, commands and contextual detail.

[Official reference](https://fluent2.microsoft.design/)

### Spectrum

**Alternative.** An established design language with detailed interaction and accessibility guidance.

**Tradeoff.** Design guidance and the chosen React implementation can differ in coverage.

> Map date, selection and error semantics to the matching implementation before committing the design.

[Official reference](https://spectrum.adobe.com/)

### PatternFly

**Alternative.** Platform administration, cluster operations and dense resource inventory.

**Tradeoff.** A mature admin vocabulary can still need domain-specific content and navigation.

> Give resource status, namespace and last observed time separate fields in the inventory.

[Official reference](https://www.patternfly.org/)

### USWDS

**Alternative.** Public-service experiences needing clear forms and accessible layout guidance.

**Tradeoff.** Check the service's own accessibility, language and brand obligations.

> Use one question per decision and show corrective text that identifies the field and recovery action.

[Official reference](https://designsystem.digital.gov/)

### GOV.UK Design System

**Alternative.** Transactional services involving eligibility, application, review and confirmation.

**Tradeoff.** Adapt local policy and language and retain the user's own visual identity.

> Use a check-answers pattern before submission and a confirmation reference afterwards.

[Official reference](https://design-system.service.gov.uk/)

## Motion & visualisation

### Motion for React

**Default.** State-driven layout, entry and exit transitions for a live interface.

**Tradeoff.** Repeated layout animations compete with streaming updates. Respect reduced motion.

> Animate a handoff once when its persisted edge event arrives. Keep a static arrow and text for reduced motion.

[Official reference](https://motion.dev/docs/react)

### GSAP

**Specialist.** Seekable timelines for replay, with MotionPathPlugin for packets moving along curved SVG edges and ScrollTrigger for explainers.

**Tradeoff.** Use one clock per property. Keep live arrival order independent of presentation time and review licensing for redistribution.

> Map a recorded event sequence to timeline labels. Seek deterministically, restore node state on scrub and use a stationary directional label under reduced motion.

[Official reference](https://gsap.com/docs/v3/GSAP/Timeline/)

### Rive

**Specialist.** Designer-authored stateful animation for a device, robot or illustrated process.

**Tradeoff.** Requires an art asset, renderer budget and fallback semantics.

> Bind the device visual to idle, processing and fault states. Publish equivalent text and a static fallback.

[Official reference](https://rive.app/docs/runtimes/web/web-js)

### React Flow

**Default.** Interactive dependency graphs with custom nodes, selection, pan and zoom.

**Tradeoff.** Layout and execution come from separate systems. Dense graphs need a timeline alternative.

> Use @xyflow/react for read-only execution topology. Inspect a node by mouse or keyboard and match its timeline row.

[Official reference](https://reactflow.dev/)

### ELK.js

**Specialist.** Automatic graph layout for branching plans or nested dependencies.

**Tradeoff.** Repeated layout causes jitter and main-thread stalls.

> Compute the layered layout in a worker on topology changes, then animate only the active edge.

[Official reference](https://github.com/kieler/elkjs)

### Apache ECharts

**Alternative.** Linked time-series views, distributions and operational metrics.

**Tradeoff.** Highly configurable charts require deliberate units, missing-data handling and accessible summaries.

> Show queue wait and tool latency separately with p50 and p95. Provide a table for the selected time window.

[Official reference](https://echarts.apache.org/en/index.html)

### MapLibre GL JS

**Specialist.** Map rendering for fleet, incident and site operations with your own style and tile choices.

**Tradeoff.** Budget tile hosting, attribution and offline behavior separately.

> Cluster sites by zoom. Selecting a marker and selecting its table row must open the same incident.

[Official reference](https://maplibre.org/maplibre-gl-js/docs/)

### deck.gl

**Specialist.** GPU-accelerated geospatial layers for dense telemetry and paths.

**Tradeoff.** Payload volume and GPU memory matter on low-end devices.

> Add a time-windowed trajectory layer over the basemap and bound the number of rendered points.

[Official reference](https://deck.gl/)

### React Three Fiber

**Specialist.** React renderer for a real 3D inspection task or digital twin.

**Tradeoff.** 3D scenes add asset weight and GPU load. Define what decision needs the extra dimension.

> Lazy-load the equipment view only on inspection, show loading state and offer a labeled 2D schematic.

[Official reference](https://r3f.docs.pmnd.rs/getting-started/introduction)

### Anime.js

**Alternative.** SVG path drawing, morphing and object-on-path motion for custom diagrams.

**Tradeoff.** Choose it for a bespoke diagram with a defined DOM owner. Avoid two animation engines writing the same property.

> Animate a single envelope along the committed edge and clear it on completion or seek.

[Official reference](https://animejs.com/documentation/svg/)

### Web Animations API

**Alternative.** Native browser animation control for simple transitions and playback using a small dependency budget.

**Tradeoff.** A path layout, timeline model and React lifecycle cleanup are your responsibility.

> Animate the committed handoff in the browser and cancel the animation when the view unmounts or the cursor jumps.

[Official reference](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API)

### D3 transitions

**Specialist.** Data joins and interpolated transitions for custom span waterfalls, distribution views and changing metrics.

**Tradeoff.** Give D3 ownership of a bounded rendering subtree and stable span keys.

> Build a duration waterfall keyed by span ID, preserve row order and update only the bars whose timestamps changed.

[Official reference](https://d3js.org/d3-transition)

### PixiJS

**Specialist.** A GPU-backed overlay for many simultaneous packet sprites or dense telemetry visuals.

**Tradeoff.** Profile first. Use an accessible DOM inspector and keep GPU coordinates in sync with pan and zoom.

> Render only visible, sampled transfer sprites; pause the ticker in background tabs and retain exact counts in the event list.

[Official reference](https://pixijs.com/8.x/guides/components/scene-objects/particle-container)

### Sigma.js

**Specialist.** WebGL network exploration when the problem is a large network of relationships.

**Tradeoff.** Rich editable HTML nodes and form-heavy operator workflows favor a different renderer.

> Map the service dependency network at overview zoom and drill into one run for its exact sequence and decisions.

[Official reference](https://www.sigmajs.org/)

### dotLottie-web

**Specialist.** Playback of authored vector motion assets for reusable illustrations and state cues.

**Tradeoff.** An asset alone cannot encode changing topology, payloads or audit semantics.

> Bind a short completion or fault asset to a committed state. Preserve visible status text and offer a still frame.

[Official reference](https://developers.lottiefiles.com/docs/dotlottie-player/dotlottie-web/)

### View Transition API

**Alternative.** Shared visual continuity between a list item and its detail screen.

**Tradeoff.** Check platform support and avoid two engines animating the same element.

> Provide a plain navigation path and honor reduced motion when transitioning between case and detail.

[Official reference](https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API)

## Data interaction

### TanStack Table

**Default.** Headless sorting, filtering and column models for queues built to your own design system.

**Tradeoff.** You implement semantics, keyboard behavior, pagination UI and rendering.

> Build a URL-filtered queue with stable row IDs and preserve the selected run when the sort changes.

[Official reference](https://tanstack.com/table/latest)

### TanStack Virtual

**Specialist.** Window long timelines and lists whose DOM cost becomes measurable.

**Tradeoff.** Dynamic row heights and keyboard focus require testing.

> Virtualize the event history, preserve the scroll anchor, and announce new rows without stealing focus.

[Official reference](https://tanstack.com/virtual/latest)

### AG Grid

**Alternative.** Spreadsheet-like analysis with commercial options for pivoting, grouping and server-side row models.

**Tradeoff.** Check feature entitlement and licensing before choosing a grid module.

> Use Enterprise only when pivot or the Server-Side Row Model is required and licensed. Specify large-data tests.

[Official reference](https://www.ag-grid.com/react-data-grid/community-vs-enterprise/)

### TanStack Query

**Default.** Server-state cache for authorized run lists, evidence and details.

**Tradeoff.** A query cache shared across tenant switches can expose stale data.

> Scope query keys to tenant and run, cancel stale queries on switch, and clear tenant data on sign-out.

[Official reference](https://tanstack.com/query/latest)

### React Hook Form

**Default.** Performance-conscious forms for case intake and reviewer decisions.

**Tradeoff.** Client errors can drift from server validation.

> Validate on submit with the shared schema, retain typed fields after a server error and focus the first invalid control.

[Official reference](https://react-hook-form.com/)

### Zod

**Default.** Runtime schemas at TypeScript boundaries for inputs, tool arguments and streamed events.

**Tradeoff.** Shape validation alone grants no authority over an object.

> Parse unknown payloads server-side, authorize referenced resources and reject unsupported event versions.

[Official reference](https://zod.dev/)

### XState

**Specialist.** Explicit client state machines for reconnect, review and replay controls.

**Tradeoff.** Duplicating the backend workflow in the browser creates conflicting states.

> Model only view modes and connection states in XState. Derive business status from ordered events.

[Official reference](https://stately.ai/docs/xstate)

## Agent interfaces

### AI Elements

**Default.** Editable UI components for messages, tool output, sources and AI-assisted workflows.

**Tradeoff.** Map runtime events to view models. Review components that display sensitive details.

> Use a tool card with name, elapsed time, scrubbed input summary and result link. Keep approvals server-authorized.

[Official reference](https://elements.ai-sdk.dev/)

### assistant-ui

**Alternative.** Conversation-first React UI with thread primitives and runtime integration.

**Tradeoff.** A chat thread alone gives poor visibility into parallel work.

> Attach a thread to the selected run and preserve links from each tool result to its evidence.

[Official reference](https://www.assistant-ui.com/docs)

### CopilotKit

**Alternative.** Embedded copilots that read scoped application context and expose interactive actions.

**Tradeoff.** Define exactly which state and actions a user session may share.

> Mount a contextual copilot on one case. Confirm each write through the same server policy as a normal button.

[Official reference](https://www.copilotkit.ai/)

### AG-UI

**Alternative.** Event protocol between different agent runtimes and interactive clients.

**Tradeoff.** Choose supported event types and version an adapter to the business event log.

> Map run, tool and lifecycle updates through an adapter and preserve your own replay cursor.

[Official reference](https://docs.ag-ui.com/introduction)

### json-render

**Specialist.** Schema-constrained generative UI from a registered component and action catalog.

**Tradeoff.** Models need a small catalog, strict validation and an ordinary fallback for invalid specs.

> Allow Summary, EvidenceList and ApprovalRequest. Validate props and authorize any action on the server.

[Official reference](https://json-render.dev/)

### A2UI

**Specialist.** Declarative UI descriptions for an agent to request widgets across renderer implementations.

**Tradeoff.** Confirm schema and renderer compatibility before promising a cross-client feature.

> Negotiate a supported catalog, reject unknown actions and provide a generic read-only fallback.

[Official reference](https://a2ui.org/)

### Streamdown

**Specialist.** Streaming Markdown rendering when prose arrives incrementally.

**Tradeoff.** Treat links and embedded content as untrusted and constrain optional heavy renderers.

> Keep partial Markdown readable, restrict link schemes, and render code as text until the fence is closed.

[Official reference](https://streamdown.ai/)

## Interaction primitives

### Floating UI

**Alternative.** Positioning an anchored inspector, tooltip or contextual menu in complex layouts.

**Tradeoff.** Positioning alone does not supply dialog semantics or a focus policy.

> Keep the inspector visible near the selected item on scroll and test Escape and focus return.

[Official reference](https://floating-ui.com/docs/getting-started)

### Ariakit

**Alternative.** A custom React design system with accessible menu, combobox and dialog behavior.

**Tradeoff.** Visual treatment, integration testing and component composition are team responsibilities.

> Test a long combobox with a keyboard, a screen reader and an input-method editor.

[Official reference](https://ariakit.org/)

### Headless UI

**Alternative.** Unstyled accessible components for an existing Tailwind-based interface.

**Tradeoff.** Avoid mixing separate overlay stacks across teams without a shared focus contract.

> Use the dialog primitive for review and restore focus to the invoking queue action.

[Official reference](https://headlessui.com/)

## Charts & diagrams

### Recharts

**Specialist.** Conventional React dashboards with composable Cartesian charts.

**Tradeoff.** High mark counts and bespoke interactions need device-level profiling.

> Plot queue age and tool latency on separate charts with labeled units and a table alternative.

[Official reference](https://github.com/recharts/recharts)

### Observable Plot

**Specialist.** Exploratory operational charts where a concise statistical grammar is valuable.

**Tradeoff.** Product-level interaction and persistent selection need surrounding state management.

> Facet queue delay by region and include sample size for each distribution.

[Official reference](https://observablehq.com/plot/what-is-plot)

### Vega-Lite

**Specialist.** Reusable declarative chart specs for linked operational analytics.

**Tradeoff.** A generated chart specification still needs schema, dataset and URL restrictions.

> Allow an approved chart schema and a bounded field catalog; fail gracefully on invalid encodings.

[Official reference](https://vega.github.io/vega-lite/)

### Cytoscape.js

**Specialist.** Network analysis and graph selection where topology matters more than form-like nodes.

**Tradeoff.** Interactive complexity, layout cost and accessibility need separate design.

> Filter services by neighborhood and link selected nodes to an equivalent textual dependency view.

[Official reference](https://js.cytoscape.org/)

### Graphviz

**Specialist.** Reproducible static architecture and dependency diagrams from structured topology.

**Tradeoff.** Large diagrams can become illegible despite automatic layout.

> Split trust boundaries and runtime flows across diagrams. Label edge direction and protocol.

[Official reference](https://graphviz.org/)

### Mermaid

**Specialist.** Maintaining architecture, state and sequence diagrams beside design decisions.

**Tradeoff.** Renderer capabilities differ between documentation hosts.

> Use stable names and one decision per diagram. Verify rendering on the publishing target.

[Official reference](https://mermaid.js.org/intro/)

### visx

**Specialist.** Bespoke React visualizations requiring control over scales and marks.

**Tradeoff.** The team owns axes, legends, keyboard navigation and accessible explanations.

> Build a tool-span waterfall with consistent time scales and links to textual span details.

[Official reference](https://airbnb.io/visx/)

### Konva

**Specialist.** A canvas-based floor plan, equipment editor or layered inspection surface.

**Tradeoff.** A canvas needs a parallel semantic interaction path and explicit hit testing.

> Synchronize canvas selection with a keyboard-accessible equipment list.

[Official reference](https://konvajs.org/docs/)

### Three.js

**Specialist.** A 3D inspection where orientation or occlusion changes an operator's decision.

**Tradeoff.** Asset budget, GPU availability and camera controls affect actual usability.

> Define the inspection question, lazy-load the model and provide a labeled 2D fallback.

[Official reference](https://threejs.org/docs/)

## Localization

### FormatJS

**Alternative.** Localized messages, plural forms and dates for internationalized web applications.

**Tradeoff.** Extracted keys and translations require an ownership and release workflow.

> Format numeric counts by locale and keep opaque case identifiers untranslated.

[Official reference](https://formatjs.github.io/docs/intl/)

### i18next

**Alternative.** Runtime locale selection and resource namespaces across multiple clients.

**Tradeoff.** Lazy-loaded namespaces can produce partial screens or fallback leaks.

> Test a missing translation and language switch in the middle of an approval journey.

[Official reference](https://www.i18next.com/)

## Design operations

### Style Dictionary

**Alternative.** Distributing design tokens to several web and native clients.

**Tradeoff.** Build transforms can diverge by platform or silently change token meaning.

> Produce light, dark and high-contrast outputs from semantic aliases and review visual diffs.

[Official reference](https://styledictionary.com/)

### Design Tokens Community Group format

**Alternative.** A portable token exchange format between design tools and platform builds.

**Tradeoff.** Validate tool support for the selected specification revision and alias behavior.

> Specify semantic color and motion tokens once and validate aliases before generating platform values.

[Official reference](https://www.designtokens.org/tr/2025.10/format/)

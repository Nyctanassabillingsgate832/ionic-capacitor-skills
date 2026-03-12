# Ionic Capacitor Skill for Claude Code

> Build production-quality, native-feeling mobile apps with AI assistance. This Claude Code skill teaches Claude the correct patterns for Ionic Framework + Capacitor across React, Angular, and Vue.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJ3aGl0ZSI+PHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyczQuNDggMTAgMTAgMTAgMTAtNC40OCAxMC0xMFMxNy41MiAyIDEyIDJ6bTAgMThjLTQuNDIgMC04LTMuNTgtOC04czMuNTgtOCA4LTggOCAzLjU4IDggOC0zLjU4IDgtOCA4eiIvPjwvc3ZnPg==)](https://docs.anthropic.com/en/docs/claude-code)
[![Ionic](https://img.shields.io/badge/Ionic-8.x-3880ff?style=for-the-badge&logo=ionic&logoColor=white)](https://ionicframework.com/)
[![Capacitor](https://img.shields.io/badge/Capacitor-6.x-119eff?style=for-the-badge&logo=capacitor&logoColor=white)](https://capacitorjs.com/)

---

## The Problem

When you ask AI to build an Ionic Capacitor app, it often gets the **Ionic-specific patterns wrong**:

- Uses `useEffect`/`onMounted` instead of Ionic lifecycle hooks (`useIonViewWillEnter`) -- pages don't refresh data when navigated back to
- Applies `dark` CSS class instead of `ion-palette-dark` -- dark mode doesn't work
- Uses `<IonList>` for photo galleries instead of `<IonGrid>` -- no responsive columns
- Misses `<IonPage>` wrappers -- page transitions and scrolling break
- Skips skeleton loading (`<IonSkeletonText>`) -- app feels sluggish
- Doesn't use `standalone: true` for Angular -- outdated NgModule patterns
- Forgets `addIcons()` registration -- icons don't render

## The Solution

This skill injects the correct patterns, best practices, and component knowledge directly into Claude's context. **Benchmarked at 100% pass rate** across React, Angular, and Vue test cases.

### Before vs After

| Pattern | Without Skill | With Skill |
|---------|:---:|:---:|
| Ionic lifecycle hooks | Missed | Used correctly |
| Dark mode class (`ion-palette-dark`) | Wrong class | Correct |
| Photo gallery layout | `IonList` (single column) | `IonGrid` (responsive) |
| Skeleton loading | Skipped | Included |
| Angular standalone imports | Sometimes missed | Always correct |
| Sheet modals with breakpoints | Sometimes missed | Always correct |
| Form validation patterns | Basic | Framework-idiomatic |

**Benchmark: 100% with skill vs 90.5% without** (42/42 assertions passed across 6 evals)

---

## Quick Start

### Install the Skill

```bash
# Download and install
curl -LO https://github.com/gabriel-tutor/ionic-capacitor-skills/releases/latest/download/ionic-capacitor.skill
claude skill install ionic-capacitor.skill
```

Or clone and install from source:

```bash
git clone https://github.com/gabriel-tutor/ionic-capacitor-skills.git
claude skill install ionic-capacitor-skills/ionic-capacitor
```

### Use It

Once installed, just ask Claude to build your app. The skill activates when it detects Ionic/Capacitor context:

```
> Build a fitness tracker app with Ionic React. Include tab navigation,
  pull-to-refresh, swipe-to-delete on activities, and skeleton loading.
```

```
> Create a camera app with Ionic Angular using standalone components.
  Display photos in a responsive grid gallery. Persist with Capacitor Preferences.
```

```
> Build a task manager with Ionic Vue using Pinia. Group tasks in accordions,
  add a sheet modal for creating tasks, and include dark mode toggle.
```

---

## What's Inside

```
ionic-capacitor/
├── SKILL.md                    # Main skill (project setup, components, theming, native APIs, deployment)
├── evals/
│   └── evals.json              # 6 eval test cases with 42 assertions
└── references/
    ├── components.md           # Complete reference of all 94 Ionic UI components
    ├── native-plugins.md       # All 24 Capacitor plugins with code examples
    ├── styling.md              # CSS utilities, Shadow Parts, custom properties, responsive design
    ├── production.md           # Error handling, security, accessibility, debugging, performance
    ├── react.md                # React patterns: hooks, routing, Zustand/TanStack Query
    ├── angular.md              # Angular patterns: standalone components, signals, OnPush
    └── vue.md                  # Vue patterns: Composition API, Pinia, composables
```

### Coverage

**Frameworks:** React, Angular, Vue (all first-class)

**Components:** All 94 Ionic components organized by category -- Layout, Navigation, Tabs, Menu, Toolbar, Buttons, Cards, Lists, Forms, Overlays, Grid, Date/Time, Media, and more

**Capacitor Plugins:** All 24 official plugins -- Camera, Geolocation, Push Notifications, Filesystem, Preferences, Haptics, StatusBar, SplashScreen, App, Browser, Clipboard, Device, Keyboard, Network, Share, Local Notifications, Dialog, Action Sheet, Toast, App Launcher, Motion, Screen Reader, Text Zoom, Google Maps

**Topics Covered:**
- Project setup and configuration (`capacitor.config.ts`, `ionic.config.json`)
- Page structure (`IonPage > IonHeader > IonContent`)
- Navigation (tabs, side menu, stack navigation)
- Lists with sliding actions (`IonItemSliding`)
- Responsive grid layouts (`IonGrid > IonRow > IonCol`)
- Forms with validation and proper label placement
- Overlays (modals, alerts, action sheets, toasts)
- Pull-to-refresh and infinite scroll
- Skeleton loading for perceived performance
- CSS utility classes (`ion-padding`, `ion-text-center`, responsive visibility)
- CSS Shadow Parts and custom properties for component customization
- Theming with CSS custom properties
- Dark mode (system, always, toggle with `ion-palette-dark`)
- Error handling patterns for native APIs (try/catch, user cancellation)
- Platform detection (`Capacitor.isNativePlatform()`, web fallbacks)
- Offline handling with Network plugin and Preferences caching
- Security best practices (XSS, CSP, secure storage)
- Accessibility (ARIA, Screen Reader, keyboard navigation)
- Debugging on devices (Safari Web Inspector, chrome://inspect)
- App icons and splash screens (`@capacitor/assets`)
- Performance optimization (lazy loading, image optimization, virtual scroll)
- Deployment to iOS App Store and Google Play

---

## Benchmark Results

Tested across 6 realistic app-building scenarios with 7 assertions each (42 total):

| Eval | Framework | With Skill | Without Skill |
|------|-----------|:---:|:---:|
| Fitness Tracker | React | 7/7 (100%) | 5/7 (71%) |
| Camera Photos | Angular | 7/7 (100%) | 6/7 (86%) |
| Task Manager | Vue | 7/7 (100%) | 6/7 (86%) |
| Notification & Styling | React | 7/7 (100%) | 7/7 (100%) |
| Location Explorer | Angular | 7/7 (100%) | 7/7 (100%) |
| Notes with Offline | Vue | 7/7 (100%) | 7/7 (100%) |
| **Overall** | | **42/42 (100%)** | **38/42 (90.5%)** |

**Key differentiators** -- patterns the skill gets right that Claude misses without it:
- `useIonViewWillEnter` / `onIonViewWillEnter` lifecycle hooks (vs `useEffect` / `onMounted`)
- `IonGrid` with `IonCol` for responsive galleries (vs CSS grid or single-column `IonList`)
- `IonSkeletonText animated` for loading states (vs `IonSpinner`)
- Consistent error handling patterns across all native API calls

---

## How Claude Code Skills Work

[Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code) are reusable prompt packages that give Claude specialized knowledge. When you install a skill:

1. **Claude sees the skill name + description** in its available skills list
2. **When relevant**, Claude reads the full `SKILL.md` and applies its patterns
3. **For framework-specific tasks**, Claude reads the appropriate reference file (e.g., `references/react.md`)

Think of it as giving Claude an expert cheat sheet for Ionic + Capacitor development.

---

## Contributing

Found a pattern that Claude gets wrong? PRs welcome!

1. Fork the repo
2. Edit the relevant file (`SKILL.md` or `references/*.md`)
3. If adding a new pattern, consider adding an eval assertion in `evals/evals.json`
4. Submit a PR with a description of what pattern you fixed/added

### Running Evals

The `evals/` directory contains test prompts and assertions. To run them, you'll need the [skill-creator](https://github.com/anthropics/claude-code-plugins) plugin for Claude Code.

---

## License

MIT License -- see [LICENSE](LICENSE) for details.

---

## Star History

If this skill helps you build better Ionic apps with Claude, please star the repo! It helps other developers discover it.

---

Built with [Claude Code](https://claude.com/claude-code) and the [Skill Creator](https://github.com/anthropics/claude-code-plugins) plugin.

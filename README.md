# EnerFlux

Adaptive renewable microgrid optimization simulator for a small community.

Simulates solar PV, wind turbines, a hydroelectric dam, battery storage, and variable community demand, then runs a weighted multi-objective optimization engine that dispatches generation to minimize cost, CO₂ emissions, battery degradation, and renewable curtailment while meeting demand. Every dispatch decision comes with an observation → constraint → action explanation.

## Features

- Canvas-rendered parallax landscape with animated energy-flow particles
- Multi-objective optimization across 4 modes: Balanced, Cost, Low Carbon, Battery Life
- Grid stress tests (solar drop, wind failure, hydro failure, demand spike, low battery, storm, cascade event) with before/after comparison
- 24-hour forecast with hour-by-hour simulation and weather controls
- Naive rule-based control vs. EnerFlux optimization comparison, showing real savings

## Tech

React + TypeScript + Vite. Canvas 2D for the landscape/particle rendering, no other frameworks or UI libraries.

```
index.html
src/
  types.ts, weatherProfiles.ts, optimization.ts, simulation.ts, engine.ts   pure simulation/optimization logic
  store.ts                                                                  external store bridging engine state into React
  landscape/render.ts                                                       canvas draw routines
  components/                                                               App, Nav, section components, LandscapeCanvas
  main.tsx, styles.css
```

## Run

```
npm install
npm run dev       # dev server
npm run build     # production build -> dist/
npm run preview   # serve the production build locally
```

# AI-Based Warehouse Robot Simulation

A browser-based warehouse robot simulation built with React and Tailwind CSS. Robots navigate a grid warehouse using the BFS pathfinding algorithm, re-routing around obstacles in real time, while a live dashboard tracks task completion and distance travelled.

## Features

- Grid-based warehouse layout
- Autonomous robot navigation using BFS pathfinding
- Obstacle detection with dynamic re-routing
- Live dashboard showing task completion and distance metrics
- Responsive UI

## Tech Stack

- React 19
- Vite
- Tailwind CSS
- JavaScript (BFS pathfinding algorithm)

## How It Works

The warehouse is represented as a 6x6 grid. Each robot needs to reach a target cell (a pickup or delivery point) while avoiding obstacle cells placed on the grid.

Pathfinding is done with a standard BFS (breadth-first search): starting from the robot's position, it explores neighboring cells layer by layer, tracking visited cells so it never revisits a node, until it reaches the target. The four possible directions are shuffled before each expansion, so robots don't all take the same predictable route through the grid.

If an obstacle blocks the current path, the robot recalculates using the same BFS logic against the updated grid, so it re-routes instead of getting stuck.

The dashboard reads the robots' live positions and paths and renders task progress and distance travelled as they move.

## Project Structure

```
warehouse-robot-simulation/
├── public/
│   ├── favicon.svg
│   └── icons.svg
├── src/
│   ├── App.jsx          # Landing page / entry point
│   ├── Dashboard.jsx     # Grid, robots, BFS pathfinding, live stats
│   ├── main.jsx          # React root
│   ├── index.css
│   └── assets/
├── index.html
├── tailwind.config.js
└── vite.config.js
```

## Screenshots

<!-- Add a screenshot or GIF of the dashboard here, e.g.: -->
<!-- ![Dashboard](./src/assets/dashboard-preview.png) -->

## Running Locally

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
```

## Deployment

Deployed on Vercel.

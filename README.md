# WalkWithMe

NYC subway navigation that works underground, with no signal. Built at the WinC Builder Sprint (NYU, Nov 2026).

**Type where you're going and WalkWithMe does the rest.** It finds your nearest station from GPS (which works without data), shows the best route and alternatives with arrival times, and counts down your stops in ride mode. No AI, no internet needed.

## Features
- Offline-first: all stations, lines and routing are built into the page. After the first visit, a service worker lets it reopen with zero signal.
- Best route and alternatives (fastest, fewest changes, least walking), each with total time and arrival time.
- Ride mode: a countdown of stops left, plus an "up next" list, spoken alerts and vibration. You tap at each stop, so it needs no GPS underground.
- Arrival times: live when online, last saved times when offline, or "internet needed".
- Saved journeys, larger text and a Tunnel mode demo switch.

## Run
Open `index.html`, or turn on GitHub Pages (Settings → Pages → Deploy from branch → `main` / root).

## Live arrivals
`fetchArrivals()` in `index.html` uses a mock feed (`LIVE_SOURCE = 'demo'`). To use real MTA data, point `LIVE_SOURCE` at a small proxy that reads the MTA GTFS-realtime feed and returns `{ "arrivals": [epochMs, ...] }` for a stop, line and direction.

## Coverage
This prototype covers 8 lines (R Q 1 6 A F L 7) with typical weekday service.

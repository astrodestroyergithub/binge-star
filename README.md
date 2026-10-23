# BingeStar (JioHotstar Clone) — Netlify Production Bundle

## Overview
**BingeStar** is a responsive streaming platform modeled on **JioHotstar**, featuring a dynamic personalization engine (**BingeEngine v4.2**) that prevents repetitive content across login sessions.

## System Design Features Included
1. **Multi-Armed Bandit Recommendation Engine (`ε = 0.25`)**: Combines 75% user affinity exploitation (genre/language weights) with 25% session-seeded exploration so every login surfaces fresh movies, series, and row orderings.
2. **Deterministic Session PRNG (`Mulberry32`) & Temporal Cohorting**: Salted by session count and time-of-day bucket (`Morning Express`, `Afternoon Binge`, `Prime Time 4K`, `Late Night Cinema`).
3. **Real-Time Sports Telemetry & Concurrent Viewer Ticker**: Simulated live scorecards (`IND vs AUS`, `TATA IPL`, `Premier League`) with dynamic viewer counts.
4. **Dynamic Promotional Offer Engine**: Rotates contextual subscription bundles and coupon codes per user cohort.
5. **Client-Side Edge Cache (`localStorage` + Fallback)**: Persists Watchlist, Continue Watching progress bars, active Profile, and Bandit reward boosts.

## Deploying to Netlify
- **Drag & Drop**: Drag the unzipped `bingestar-netlify` folder directly into [app.netlify.com/drop](https://app.netlify.com/drop).
- **Git CI/CD**: Push this folder to GitHub/GitLab and connect to Netlify (`Publish directory: .`, no build command needed).

# Arceus Ascendants — Cynthia's Gauntlet

## Overview

Arceus Ascendants is an optimized Pokémon battle team developed for Cynthia's Gauntlet, organized by Custodia.

Our solution combines strategic team composition, optimized movesets, and a custom decision-making policy designed to maximize battle win rate.

## Tournament Performance

| Metric | Result |
|---|---:|
| Tournament Win Rate | 97.600% |
| Average Turns | 13.2 |
| Without Custom Policy | 97.500% |

## Team Composition

| Pokémon | Move 1 | Move 2 | Move 3 | Move 4 |
|---|---|---|---|---|
| Swinub | Bite | Take Down | Ice Beam | Earthquake |
| Grovyle | Energy Ball | Brick Break | Aerial Ace | Rock Slide |
| Slaking | Thunderbolt | Thunder Punch | Ice Punch | Earthquake |
| Sneasel | Ice Punch | Quick Attack | Brick Break | Aerial Ace |
| Ekans | Earthquake | Seed Bomb | Gunk Shot | Rock Slide |
| Weavile | Ice Punch | Night Slash | Brick Break | Aerial Ace |

## Custom Battle Policy

The custom policy evaluates legal battle actions using:

- Expected damage calculations
- Type effectiveness and STAB
- Knockout probability
- Move accuracy and priority
- Speed and stat modifiers
- Opponent threat estimation
- Intelligent forced-switch selection

The policy uses the battle state supplied by the simulator and requires no external Python dependencies.

## Optimization Methodology

The development process involved:

- Automated team and moveset optimization
- Parallel battle simulations
- Evolutionary search
- Targeted team optimization
- Multiple custom policy experiments
- Independent validation using fresh simulation seeds
- Official tournament evaluation

The final configuration was selected based on its official tournament performance.

## Repository Structure

- `team.json` — Final optimized team configuration
- `policy.py` — Custom battle decision-making policy
- `README.md` — Project documentation
- `.gitignore` — Git exclusion rules

## How to Run

1. Visit [Cynthia's Gauntlet](https://cynthias-gauntlet.onrender.com/).
2. Load the team configuration from `team.json`.
3. Upload `policy.py` as the custom battle policy.
4. Run the tournament evaluation.

For local validation, use the official simulator provided by the organizers.

## Team

**Arceus Ascendants**

Developed for Cynthia's Gauntlet — Custodia.
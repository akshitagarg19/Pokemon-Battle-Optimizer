# Cynthia's Gauntlet: Team Submission

**Custodia × WiTS, IIT Madras**

## Team

| # | Pokémon | Cost | Moves | Role |
|---|---|---|---|---|
| 1 | Slaking | 13 | Earthquake, Ice Punch, Strength, Thunder Punch | Lead. Highest base stats in the pool (BST 670). Ice, Ground and Electric hits answer Garchomp, Lucario and Milotic early. |
| 2 | Grovyle | 6 | Leaf Blade, Giga Drain, Aerial Ace, Brick Break | Fast Grass attacker for Milotic and Ground types. Giga Drain gives sustain. |
| 3 | Zigzagoon | 2 | Ice Beam, Seed Bomb, Surf, Thunder | Cheap special attacker that covers Ice, Grass, Water and Electric. |
| 4 | Weavile | 9 | Ice Punch, Night Slash, Brick Break, Aerial Ace | Fastest member. Ice Punch for Garchomp, Night Slash for Spiritomb, Brick Break for Lucario. |
| 5 | Sentret | 2 | Double-Edge, Ice Punch, Ice Beam, Flamethrower | Cheap mixed attacker. Flamethrower handles Steel types. |
| 6 | Lopunny | 8 | Ice Punch, Fire Punch, Strength, Thunder Punch | Fast physical finisher with three elemental punches. |

**Total cost: 40 / 40.** There are no legendary or mythical Pokémon, and every move is a supported Gen 4 move. The team passes `engine.validator.validate_team` and the simulator's web validator ("Team is Legal!").

## Strategy

1. **Coverage over counters.** Hidden variants may change Cynthia's team and behaviour, so the team is built for broad type coverage rather than to beat one fixed line-up:
   - Six Pokémon carry Ice moves, so there is always an answer to Garchomp.
   - Fire and Electric moves handle Lucario, Milotic and Steel types.
   - Grass and Dark moves handle Water, Ground and Ghost types.
2. **Spend the budget where stats matter.** Slaking and Weavile take 22 points between them. Two-point Zigzagoon and Sentret fill the remaining slots with full-coverage movesets.
3. **Every move does damage.** No status or set-up moves. Each slot carries four damaging moves, so the baseline policy always has a strong attack to choose, and wins end quickly (this also helps the turns tie-break).
4. **Tuned by measurement.** The team was chosen by searching a large set of team and moveset candidates in the local simulator, then confirmed on fresh seeds it was never tuned on.
5. **Why no custom policy.** Several hand-written and search-based policies were tested. On held-out seeds, none of them beat the baseline policy with this team, so the baseline plays every turn and the submission never falls back to it.

## Results (local, held-out seeds)

Fresh seeds that were not used for tuning, run with the simulator included in the tournament ZIP:

| Variant (practice) | Battles | Win rate | Avg turns in wins |
|---|---|---|---|
| Public | 300 | 92.3% | 12.8 |
| Aggressive style | 300 | 95.0% | 12.1 |
| Patient style | 300 | 92.0% | 13.5 |
| **Average** | **900** | **≈93%** | **≈12.8** |

The official CLI evaluation (`--eval --seeds 50`) gives **92.0%** (46/50), with 12.46 average turns in won battles.

Notes:
- "Aggressive" and "Patient" are local copies of the public variant with only the bot style changed.
- The hidden variants were not read or used, as the Fair Play rules require.

## How to run

Requirements: Python 3.10+. The simulator from `CynthiaXCustodia.zip` needs no extra packages.

Copy `team.json` into the root of the extracted simulator folder, then run the commands below from that folder.

```bash
# validate the team
python -c "import json; from engine.validator import validate_team; print(validate_team(json.load(open('team.json'))))"

# one battle with a readable log
python -m engine.runner --team team.json --seed 7

# multi-seed evaluation
python -m engine.runner --team team.json --eval --seeds 100

# browser UI: open the printed URL, paste the team, run battles
python -m ui.server 8000
```


## Team Members
Akshita Garg
Ansh Varshney


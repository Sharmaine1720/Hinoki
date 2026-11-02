# Hinoki Village Treasure Hunt

A static browser game for Grade 5 EFL students: 20 short questions, two choices each, six animated surprise games, and a final score out of 100. Questions model “You can …”.

## Run and share

Open `index.html` beside the PNG in a modern browser, or serve this folder:

```sh
cd /workspace/Hinoki
python3 -m http.server 8000 --bind 0.0.0.0
```

No build, dependencies, API keys, or backend are needed. GitHub Pages can deploy `main`, `/ (root)`. Progress is saved locally in this browser; use **Start over** between students on a shared device. Scores are practice results, not secure teacher submissions.

## Map and controls

Each of the six areas connects to the village road network. Selecting an area makes Pikmin follow a shortest road route from its current location to that area. Completed-area roads glow pink and checkpoints get checkmarks. Areas can be visited in any order. **Next area** suggests an unfinished destination. All questions and surprise games must be completed before the finish unlocks; Pikmin then walks to the on-map finish flag.

Phones keep the route and character over the map with large area buttons underneath. Tab/Enter work throughout; Escape returns to the map. **Sound** is off initially and can be toggled on. Walking, flip, dice, and celebration animations honor reduced-motion preferences; there are no flashing effects. Current map location, question progress, memory progress, and surprise outcomes survive refreshes.

## Surprise games

| Area | Activity | Points |
|---|---|---|
| Gallery | 3×3 memory board: four pairs plus one treasure tile | All 9 tiles cleared with 0–2 mismatches: +10; 3–5: +5; 6+: −5 |
| Bazaar | Watch the diamond house, then choose after a shuffle | +10 diamond, +5 coin, −5 leaf |
| Food & Drinks | Spin the animated snack wheel | +10, +5, or −5 |
| Souvenirs | Open a bouncing mystery gift | +10 diamond, +5 coin, −5 leaf |
| Time Tunnel | Roll the dice | 6: +10; 4–5: +5; 1–3: −5 |
| Life & Creative | Stop a moving paintbrush | Gold (40–60%): +10; green (20–80%): +5; outside: −5 |

The memory board has a preview, then students find all four pairs and the single treasure card. Mismatched cards flip back; matched cards remain revealed. Progress and mismatch counts are retained when leaving or reloading. There is no timer. Treasure is a special single tile because nine tiles cannot form only pairs.

Each game awards points once. Leaving before finishing keeps the area unfinished; returning resumes it. Final outcomes are saved before reveal animations so refreshes cannot reroll or duplicate points. The new edition has a separate saved-progress key from older versions.

## Scoring

English points = correct first answers × 5. Surprise points are separate. During play the combined **provisional score is capped at 99**, even if bonus points would raise it higher. A final score up to 100 is available only once all 20 questions and all six surprise games are done. The final combined score is floored at 0 and capped at 100; completing everything does not guarantee 100. No certificate: students see their final score, English accuracy, and surprise points. **View final score** reopens it.

## Teacher edits

Edit the `areas` object in `index.html`: `q` is the question, `a` contains two choices, `correct` is 0 or 1, and `why` models the full correct sentence. There are four questions each in Gallery and Bazaar and three in each other area. Map locations and connecting paths are approximate gameplay locations.

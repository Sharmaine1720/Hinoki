# Hinoki Village Treasure Hunt

A browser game for English practice: explore six areas on the supplied village map, answer 20 questions, and earn up to 100 points. Each first answer is worth 5 points when correct. Explanations appear after every answer, followed by a printable explorer certificate.

## Play

Open `index.html` in a modern browser, keeping the PNG image in the same folder. No build or dependencies are required.

For reliable saved progress, serve the folder over HTTP:

```sh
cd /workspace/Hinoki
python3 -m http.server 8000 --bind 0.0.0.0
```

Enter your name, press **Start Adventure**, and select an area. Progress is saved in this browser when storage is available. **Start over** clears it for a new player. This is a shared-device classroom activity, so reset between students. Scores are local practice results, not secure submissions to a teacher.

On phones, area buttons appear below the map. Keyboard users can use Tab, Enter, and Escape; Escape returns from a challenge to the map. After finishing, **View certificate** reopens the result for printing or saving as PDF.

## Share online

The repository is a static site. On GitHub, enable Pages under **Settings → Pages**, choose **Deploy from a branch**, and select `main` and `/ (root)` after these files are committed and pushed. No API keys or backend are needed.

## Edit questions

Edit the `areas` object in `index.html`. Each question has text (`q`), two choices (`a`), a zero-based correct answer index (`correct`), and an explanation (`why`). The supplied set has 20 questions. Markers are approximate game locations, not verified official boundaries.

## Grade 5 edition

The 20 short questions focus on “You can …” and shops on the teacher’s map. Gallery and Bazaar have four questions each; the other four areas have three each. Each correct first answer earns 5 points, for a maximum of 100. Feedback models the full sentence.

## Area surprise games

Each area ends with a different surprise game:

| Area | Game | Points |
|---|---|---|
| Gallery | Remember and match two art cards | +5 match, −5 mismatch |
| Bazaar | Choose one shuffled wooden house | +10 diamond, +5 coin, −5 leaf |
| Food & Drinks | Spin the snack wheel | +10, +5, or −5 |
| Souvenirs | Open one mystery gift box | +10 diamond, +5 coin, −5 leaf |
| Time Tunnel | Roll the dice | 6: +10; 4–5: +5; 1–3: −5 |
| Life & Creative | Stop a moving paintbrush | Gold (40–60%): +10; green (20–80%): +5; outside: −5 |

English score = correct answers × 5. Surprise points are tracked separately. Final game score = English score + total surprise points, capped at 100 and floored at 0. Clamping is applied to the combined total, not to individual rounds, so area order does not change the result. The certificate shows English accuracy and each surprise outcome separately.

Students may skip a surprise before playing for 0 points. Every area must have a completed or skipped surprise to finish. Each surprise can award points only once; outcomes are saved immediately when chosen, before animations finish, to prevent reloading or returning to the map from rerolling. Unfinished surprises can be reopened from their area. The new edition uses separate saved progress so old badge rounds do not affect point totals.

## Pikmin finish trail

A red, leaf-topped Pikmin moves one step for every fully completed area (questions plus played or skipped surprise). The trail supports any visit order and reaches the finish at six completed areas. The position is restored from saved progress. Walking and dice animations honor the browser’s reduced-motion preference.

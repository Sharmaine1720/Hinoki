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

Edit the `areas` object in `index.html`. Each question has text (`q`), four choices (`a`), a zero-based correct answer index (`correct`), and an explanation (`why`). The supplied set has 20 questions. Markers are approximate game locations, not verified official boundaries.

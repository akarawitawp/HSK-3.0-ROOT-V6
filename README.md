# HSK Radical Mind Map — React + Excel dataset

This version is based **only on the seven Excel files supplied by the user**, with 10,969 vocabulary rows. Each entry preserves its source HSK level, word, pinyin, Thai and English meanings, radical/component, and sentence where present.

## Coverage
- 10,969 entries across HSK 1–6 and combined 7–9.
- 9,850 entries have source Thai definitions and source Chinese example sentences, sentence Pinyin, and Thai sentence translations.
- 1,119 entries (mostly advanced vocabulary) do **not** have translations/examples in the supplied sheets. These are clearly marked as missing Thai definitions and get only a **study sentence** (“Today I studied the word ...”), not a genuine contextual usage example.
- **吐** appears in the HSK 5 spreadsheet; its example has been adjusted to use **tù** (vomit) rather than **tǔ** (spit), since the Thai example refers to vomiting.
- Radical groups use the `รากศัพท์/ส่วนประกอบ (部首)` column **as provided**, not inferred etymology.
- Voice via browser SpeechSynthesis; learning progress in localStorage on each browser.

## Run locally
```
npm install
npm run dev
```

## Deploy GitHub Pages
Upload the entire project, including hidden `.github/workflows/deploy.yml`. In GitHub Settings → Pages → Build and deployment choose **GitHub Actions**. Commit to main and check the Actions tab.

The website is static: no API keys, no server and no external dictionary required.

## Thai labels for radicals
Thai labels are in `src/radicalThai.json`, and shown in the radical picker, mind-map center, and selected-word detail. These are learning-oriented labels, not always historical etymologies. Unmapped components are labeled generically.

## V5 — Mind Map zoom controls
Use − / ＋, slider (40–200%), "รีเซ็ต 100%", or "ดูภาพรวม 70%". Zoom changes only the diagram, not the vocabulary panel. No additional dependencies.
\n## Smart Zoom (V6)\nZoom changes the number of visible branches, not only image size: 40–50% = up to 36; 60–70% = 30; 80–90% = 18; 100–110% = 12; 120–140% = 9; 150–170% = 7; 180–200% = 6. Multi-ring layout keeps lines from crossing the text labels. The pagination adjusts to the branch count.\n
## V7 responsive zoom
The SVG scales as a whole on zoom: its circles, Chinese text, pinyin and branches all grow on zoom-in and shrink moderately on zoom-out. The V6 branch count behavior remains. SVG max-height is explicitly disabled to prevent the old CSS from limiting magnification. Scroll the map panel to explore the enlarged map.

## V8: Part-of-speech guide
Shows Thai, Chinese and pinyin descriptions of POS codes (including Y/F/G/T), plus an expandable glossary in the word details panel.

## V9 Pastel colors
A stable pastel color is assigned to each radical/component group. Nodes, branches, vocabulary tiles, and the selected radical badge share the group color. Different radicals can reuse colors because the palette has 12 shades. Zoom, Pinyin, Thai meanings, sentences, audio and progress tracking remain unchanged.

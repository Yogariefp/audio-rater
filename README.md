# IEM Audio Rater

A single-file, browser-based tool for rating in-ear monitors (IEMs) with a structured, repeatable scoring system. No installation, no server — just open `iem-audio-rater.html` in any modern browser and start rating.

---

## Philosophy

Audio is deeply subjective. What sounds "correct" depends on your ears, your music library, your expectations, and frankly your mood that day. This tool doesn't try to tell you what's good — it helps you articulate *why something sounds good to you*, consistently, across different IEMs.

The core ideas behind the scoring system:

**Repeatability over authority.** Anyone can say "the bass is nice." This tool forces you to decide: is the sub-bass a 6 or a 7? That distinction — made against a fixed reference — means your rating for IEM #3 is actually comparable to your rating for IEM #47 six months later.

**Your reference track matters more than the score.** The number is meaningless without the context of what you tested with. Rate the same IEM with EDM and with classical and you'll get different numbers — both are correct. Always record what you tested with.

**Lower sibilance is better.** The sibilance slider is intentionally inverted: a score of 1 means perfectly smooth, and a score of 10 means ear-fatiguing harshness. This reflects the real-world priority — you want less of it.

**Price context is built in.** A $25 IEM scoring 6.5 is remarkable. A $300 IEM scoring 6.5 is disappointing. The Value for Money criterion and the Price Range field exist so you don't lose that context six months later.

---

## How to Use

### 1. Open the app
Double-click `iem-audio-rater.html`. No internet connection required.

### 2. Fill in IEM details
- **IEM Name / Model** — be specific (e.g. `Moondrop Aria 2`, not just `Aria`)
- **Driver Type** — DD, BA, Hybrid, Planar, etc.
- **Price Range** — the tier you bought it at, not MSRP if you got a deal
- **Test Music Genre / Track** — what you actually listened to during the session

### 3. Rate each criterion using the sliders (1–10)
Click **📊 Score guide** under any slider to see exactly what each number means for that criterion. The sidebar updates the overall score and breakdown bars in real time.

The 16 criteria are grouped into six weighted categories:

| Group | Criteria | Weight |
|---|---|---|
| Bass | Sub-Bass Extension, Bass Punch, Bass Clarity | 1.5× |
| Mids | Vocal Clarity, Instrument Texture, Warmth/Timbre | 1.5× |
| Treble | Treble Detail, Sibilance *(inverted)*, Air/Extension | 1.2× |
| Technical | Separation, Soundstage, Imaging | 1.2× |
| Fit & Build | Comfort, Isolation, Build Quality | 1.0× |
| Value | Value for Money | 0.6× |

### 4. Add personal notes
Free-text observations — anything that the sliders can't capture. Cable microphonics, how they sound with your specific amp, whether they need EQ.

### 5. Save your rating
Click **💾 Save Rating**. If you save again with the same IEM name, it updates the existing entry instead of creating a duplicate.

Your ratings are stored in the browser's `localStorage` and persist between sessions.

---

## Score Reference

| Score | Verdict |
|---|---|
| 9.0 – 10.0 | Legendary |
| 8.0 – 8.9 | Excellent |
| 7.0 – 7.9 | Very Good |
| 6.0 – 6.9 | Good |
| 5.0 – 5.9 | Decent |
| 4.0 – 4.9 | Mediocre |
| 3.0 – 3.9 | Poor |
| < 3.0 | Skip It |

### The formula

$$\text{Overall} = \frac{(\text{Bass} \times 1.5) + (\text{Mids} \times 1.5) + (\text{Treble} \times 1.2) + (\text{Tech} \times 1.2) + (\text{Fit} \times 1.0) + (\text{Value} \times 0.6)}{7.0}$$

Each group score is the average of its criteria. Sibilance is inverted before averaging: `effective score = 11 − slider value`.

---

## Data Persistence

**Browser localStorage** — ratings are saved automatically and survive page refreshes.

**JSON file (recommended)** — click **🗂 Save JSON** to save all ratings to a `.json` file of your choice. The app remembers the file for the session and silently updates it every time you save a new rating. Click **📂 Load JSON** to import ratings from a previous session or another device.

**Export .txt** — human-readable export of all saved ratings for archiving or sharing.

---

## Tips for Getting Consistent Results

- Use the same few reference tracks across all your ratings. Familiarity with the recording removes one variable.
- Rate immediately after a listening session, not from memory.
- Let your ears rest for a few minutes between swapping IEMs.
- If you rate the same IEM twice and get different numbers, the difference is your data — don't average it away. Write a note about what changed.

---

## License

MIT — see [LICENSE](LICENSE).

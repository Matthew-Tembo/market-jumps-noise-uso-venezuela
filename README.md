# How Much Do Markets Respond to Noise? Evidence from Oil Exposure Around the Venezuela Shock (January 2026)

**Author:** Matthew Tembo  
**Date:** 11 January 2026  

This repository contains a short event-study that tests whether a high-salience geopolitical headline is associated with (i) a statistically unusual jump in returns or (ii) a response dominated by transitory price movements and elevated uncertainty, using **USO (United States Oil Fund)** as a tradable proxy for oil exposure.

## Contents
- `paper/`
  - `matthew-tembo-market-jumps-noise-uso-venezuela-2026-01.pdf` (main paper)
  - `matthew-tembo-market-jumps-noise-uso-venezuela-2026-01.docx` (editable source)
- `notebook/`
  - `event-study-uso-venezuela.ipynb` (reproducible analysis)
- `figures/` (optional but recommended)
  - `fig1-price.png`
  - `fig2-returns-jumpband.png`
  - `fig3-rolling-vol.png`

## Method summary
Let \(P_t\) denote daily closing price and \(r_t = \ln(P_t) - \ln(P_{t-1})\) denote log returns.

- **Reaction day** \(t_0\): first trading day on or after the headline date.
- **Event window** \(W = [t_0-K, \ldots, t_0+K]\)
- **Estimation window** \(E\): pre-event window used to estimate baseline variability.
- **Jump diagnostic:** event-day z-score \(z_{t_0} = (r_{t_0}-\mu)/\sigma\); flag a jump when \(|z_{t_0}| \ge z^*\).

### Implementation parameters (as used in the paper)
- Headline date: **2026-01-03**
- Event window: **±20 trading days**
- Estimation window: **180 trading days** ending one day before reaction day
- Jump threshold: **z\* = 2.5**
- Rolling volatility window: **10 trading days**

## How to reproduce
### Option A: Run locally
1. Install Python 3.10+.
2. Install dependencies:
   - `pip install pandas numpy matplotlib requests`
3. Open and run the notebook:
   - `notebook/event-study-uso-venezuela.ipynb`

### Option B: Run in Google Colab
1. Open the notebook on GitHub.
2. Replace `github.com` with `colab.research.google.com/github.com` in the URL.
3. Run all cells.

## Notes and interpretation caveats
- USO is futures-based and can deviate from spot crude due to roll mechanics and term-structure effects (contango/backwardation).
- This work is for research/education and is not investment advice.

## Sources
- Reuters (Jan 2026): https://www.reuters.com/world/americas/view-investors-economists-react-us-capture-venezuelas-maduro-2026-01-03/
- Reuters (Jan 2026): https://www.reuters.com/business/energy/venezuela-us-talks-export-venezuelan-oil-us-sources-say-2026-01-06/
- USO fund description (USCF Investments): https://www.uscfinvestments.com/uso
- USO.US daily data (Stooq): https://stooq.com/q/d/l/?s=uso.us&i=d

## Citation
If you use this work, please cite the PDF in `paper/`.

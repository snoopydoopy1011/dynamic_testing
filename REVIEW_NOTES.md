# Review Notes

## Options Volume Profile (`Options_volume_main_current.pine copy`)
- **Volume collection**: Each strike's call/put symbols are requested individually once lists are ready, using `request.security` with volume and close to populate per-strike arrays while tracking prior prices for change calculations.【F:Options_volume_main_current.pine copy†L1533-L1578】
- **Per-strike bucketing & resets**: `f_buildStrikes` rebuilds the strike grid around a reference price, clearing all volume/price arrays, delta histories, and visuals before seeding ATM, below, and above strikes with initialized tracking slots (including confirmed deltas and five-period histories).【F:Options_volume_main_current.pine copy†L1287-L1444】
- **Session handling**: The script initializes the grid when historical data confirms, rebuilds if loaded after the open, and refreshes at each 09:30 ET open or when the reference price drifts beyond twice the strike spacing, ensuring updated anchors and implied-move baselines per session.【F:Options_volume_main_current.pine copy†L1465-L1525】
- **Table/infopanel logic**: `updateConsolidatedInfoPanel` clears and redraws a four-column info table when data is ready, stacking sections for price levels (with distance coloring), market sentiment, and consensus details with merged headers and dynamic color coding tied to thresholds.【F:Options_volume_main_current.pine copy†L635-L720】

## Dynamic Net Flow Study (`Dynamic_Price_flow.ts.txt`)
- **Oscillator math & smoothing**: Price-derived net call/put flows normalize price change by lookback range, then apply EMA smoothing and rescale to a widened vertical range for panel separation, using midpoint anchors for price/flow alignment.【F:Dynamic_Price_flow.ts.txt†L59-L101】
- **Thresholds & state**: Zero-line proximity uses a 0.01 threshold; crossover logic sets sentiment state, with percentage-distance calculations driving status labels and bubbles that surface bullish/bearish cues and zero-line touches.【F:Dynamic_Price_flow.ts.txt†L121-L175】
- **Lower-panel styling**: Declares a lower study with per-plot weights/colors (yellow price, uptick/downtick calls/puts) plus gray midpoint line, keeping visibility to regular hours and framing optional vertical session markers.【F:Dynamic_Price_flow.ts.txt†L3-L119】【F:Dynamic_Price_flow.ts.txt†L177-L200】

## Reusable elements to port
- **Volume fetch routine**: Loop-based `request.security` pulls per-strike volume/close and immediately recomputes ratios and deltas with confirmed-history safeguards to avoid bar-reset spikes—useful for any option-profile ingestion layer.【F:Options_volume_main_current.pine copy†L1533-L1669】
- **Session reset pattern**: `f_buildStrikes` plus the open/anchor refresh logic provide a template for daily reinitialization that wipes UI handles, recalculates reference prices, and reseeds tracking arrays before live updates resume.【F:Options_volume_main_current.pine copy†L1287-L1525】
- **Info-panel composition**: Consolidated panel code demonstrates merged headers, distance coloring, and ratio-driven arrows suited for compact dashboards when porting to other platforms.【F:Options_volume_main_current.pine copy†L635-L710】
- **Lower-panel plotting**: Scaling flows relative to a widened price range with EMA smoothing and distinctive color/weight assignments offers a ready-made visual recipe for lower-pane momentum/flow overlays.【F:Dynamic_Price_flow.ts.txt†L65-L119】

## Phased roadmap for the dynamic options-flow indicator
Below is the staged plan (with starter task stubs) to build and tune the TradingView dynamic options-flow study. Save alongside the review notes so follow-on tasks can reference both the script analysis and implementation goals.

1. **Baseline analysis of existing scripts** — Understand data acquisition and UI logic in `Options_volume_main_current.pine copy` plus dynamic-flow visualization patterns in `Dynamic_Price_flow.ts.txt`, noting session-handling and plotting differences.  
   _Task stub: Survey current indicators._
2. **Define option-state classifications (ATM/ITM/OTM) for 0DTE** — Set explicit rules for classifying calls/puts as ATM/ITM/OTM for the current session, considering strike proximity and underlying price.  
   _Task stub: Design 0DTE classification logic._
3. **Volume ingestion and persistence across refresh** — Ensure per-session cumulative volumes survive chart refreshes; replicate the volume-retention behavior from the profile script while recalculating ATM/ITM/OTM on reload.  
   _Task stub: Implement resilient volume accumulation._
4. **Flow-metric construction for lower-panel oscillator** — Translate classified volumes into flow metrics analogous to the ThinkScript dynamic flow (e.g., call vs. put dominance, ATM vs. OTM differentials, smoothed momentum lines).  
   _Task stub: Build flow metrics._
5. **Visualization and user controls** — Design lower-panel plots to resemble the dynamic flow indicator while exposing inputs to tune thresholds and smoothing.  
   _Task stub: Add plotting and inputs._
6. **Alerting and signaling logic** — Offer optional alerts when flows cross critical levels or change regime.  
   _Task stub: Implement alert conditions._
7. **Validation and tuning for 0DTE use** — Test intraday behavior to confirm persistence, correctness of ATM/ITM/OTM classification, and responsiveness on low-timeframe charts.  
   _Task stub: Test and tune._
8. **Documentation and rollout** — Provide usage notes emphasizing 0DTE focus and interpretation of ATM/OTM/ITM flows.  
   _Task stub: Document usage._

**Call vs. put volume emphasis**: Start with separate call/put and ATM/OTM/ITM breakdowns; raw totals alone lose key context. Visualizing ATM and OTM streams separately (with combined summary) should capture intent while keeping the lower pane readable.
